<template>
  <div class="">
    <el-collapse accordion class="accordion">
      <el-collapse-item title="Work" name="1" class="border-transparent">
        <ul v-for="post in folders" :key="post.slug">
          <NuxtLink :to="post._path">
            <li class="text-inherit">{{ post.title }}</li>
          </NuxtLink>
        </ul>
        <NuxtLink to="PageNavigation">
          see all work
        </NuxtLink>
      </el-collapse-item>
    </el-collapse>

    <NuxtLink to="about">
      about
    </NuxtLink>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { useAsyncData } from '#app';

// Define a ref for storing folders
const folders = ref([]);

// Fetch all posts from both /folders and /page
const { data: foldersPosts } = await useAsyncData('folders', () => queryContent('/')
  .sort({ numbernavigation: 1 })
  .find());

// Combine and filter the data
onMounted(() => {
  const allPosts = [...(foldersPosts.value || [])];
  if (allPosts.length) {
    folders.value = allPosts.filter(post => post.included && post.included === true && post.included !== false);
  }
});
</script>
