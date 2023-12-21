<template>
    <div>
        <blog_listing/>
    </div>
</template>

<script setup>
// import IndexOfDemo12 from './demo-12/index.vue';
import blog_listing from './blog-listing/index.vue'
    useHead({
        bodyAttrs: {
            class: "navbar-light"
        },
    })
</script>