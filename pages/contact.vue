<template>

    <div class="pr-5"><!-- dit is het hamburgermenu-->
        <Drawer />
    </div>
    <div class="container">
        <!-- <div class="mb-10"> dit is het 'terug' pijltje
            <NuxtLink to="/">
                <span>
                    <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24">
                        <path fill="currentColor" d="m6.921 12.5l5.793 5.792L12 19l-7-7l7-7l.714.708L6.92 11.5H19v1z">
                        </path>
                    </svg>
                </span>
                <span class="text-xs">Back</span>
            </NuxtLink>
        </div> -->
        <h1> contact </h1>
        <p>
            hons.emma@gmail.com <br>
            +32499814587
        </p>
        <p> message me!</p>
        <el-input v-model="input" style="width: 240px" placeholder="message ..." />
    </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
const input = ref('')
</script>