<template>
    <div class="wsmobileheader clearfix">
        <span class="smllogo">
             <NuxtLink to="/">
                    <h2 class="text-black pointer" > Journal Of Justice</h2>
                </NuxtLink>
        </span>

        <a id="wsnavtoggle" class="wsanimated-arrow" @click="toggleMobileMenu">
            <span></span>
        </a>
    </div>
</template>
<script>
export default {
    methods: {
        toggleMobileMenu() {
            // toggle body class "dark-mode"
            document.body.classList.toggle("wsactive");
        }
    }
};
</script>
