<template>
    <section ref="customScrollbar" class="custom-scrollbar">
       <div class=" ">
        <Content />
       </div>
    </section>
</template>

<script>
import Content from './components/Content.vue';

export default {
    data() {
        return {
            isMenuOpen: false,
        };
    },
    components: { Content },
    mounted() {
        this.$nextTick(() => {
            this.setScrollbarHeight();
            window.addEventListener('resize', this.setScrollbarHeight);
        });
    },
    beforeDestroy() {
        window.removeEventListener('resize', this.setScrollbarHeight);
    },
    methods: {
        setScrollbarHeight() {
            const customScrollbar = this.$refs.customScrollbar;
            customScrollbar.style.maxHeight = '100vh'; // Set max-height to 100% of viewport height
        }
    }
}
</script>

<style scoped>
/* Scoped styles to apply scrollbar to the content inside the modal */
.custom-scrollbar {
    overflow-y: auto;
}

.custom-scrollbar::-webkit-scrollbar {
    width: 7px;
}

.custom-scrollbar::-webkit-scrollbar-track {
    background: #f3f4f6;
}

.custom-scrollbar::-webkit-scrollbar-thumb {
    background: #9ca3af;
    border-radius: 5px;
}

.custom-scrollbar::-webkit-scrollbar-thumb:hover {
    background: #9ca3af;
}
</style>
