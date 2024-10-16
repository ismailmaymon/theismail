<template>
    <div v-if="detailsOpen" class="fixed inset-0 overflow-y-auto bg-white z-[1000]">
        <div>
            <div class="">
                <!-- Desktop header -->
                <div>
                    <header
                        class="h-[70px] flex px-5 sm:px-6 items-center bg-white shadow z-50 fixed right-[7px] w-full transition-padding duration-500 ease-in-out">
                        <svg @click="handleCloseModal" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2"
                            stroke="currentColor" class="w-6 h-6 text-blue-950 cursor-pointer">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 19.5 8.25 12l7.5-7.5" />
                        </svg>
                    </header>
                </div>
            </div>
            <div class="custom-scrollbar" ref="customScrollbar">
                <div>
                    <div class="background-image py-20 sm:py-36 sm:px-0 px-5">
                        <div class="sm:max-w-3xl mx-auto sm:pt-[62px] pt-[60px]">
                            <h1 class="text-white text-4xl sm:text-6xl sm:leading-[70px] text-center">{{ pokemon.title
                                }}</h1>
                            <p class="text-center text-white pt-4 sm:text-lg">{{ pokemon.overview }}</p>
                            <div class="flex justify-center mt-7">
                                <a :href="pokemon.liveLink" target="_blank">
                                    <button
                                        class="bg-white text-blue-950 px-10 py-2 rounded-lg font-medium shadow text-lg transition ease-in-out duration-300 transform button">Live
                                        Link</button>
                                </a>
                            </div>
                        </div>
                    </div>
                    <div class="container mx-auto">
                    <div class="sm:px-40 px-5">
                        <img :src="pokemon.imageUrl" alt="" class="sm:my-24 my-10 mx-auto rounded shadow">
                    </div>
                    <div class="sm:max-w-3xl mx-auto sm:px-0 px-5">
                        <h1 class="text-black text-xl sm:text-3xl sm:leading-[70px]">Project Overview</h1>
                        <p class="text-black pt-4 sm:text-lg">{{ pokemon.overview }}</p>
                    </div>
                    <div class="sm:mx-10 sm:px-0 px-5 mt-6">
                        <h1 class="text-black text-xl sm:text-3xl sm:leading-[70px]">Tools Used</h1>
                        <div class="flex flex-wrap sm:gap-4 gap-3 mt-2">
                            <div v-for="tool in pokemon.usesLanguage"
                                class="bg-blue-950 rounded text-white sm:px-5 px-2 sm:text-lg py-1">{{ tool }}</div>
                        </div>
                    </div>
                    <div class="sm:mx-10 sm:px-0 px-5 sm:my-10 my-8">
                        <h1 class="text-black text-xl sm:text-3xl sm:leading-[70px]">Links</h1>
                        <div class="flex gap-5 mt-4">
                            <a :href="pokemon.liveLink" target="_blank">
                                <button
                                    class="bg-blue-950 text-white px-7 sm:px-10 py-2 rounded-lg font-medium shadow text-lg transition ease-in-out duration-300 transform button">Live
                                    Link</button>
                            </a>
                            <a :href="pokemon.githubLink" target="_blank">
                                <button
                                    class="bg-blue-950 text-white px-7 sm:px-10 py-2 rounded-lg font-medium shadow text-lg transition ease-in-out duration-300 transform button">Github
                                    Link</button>
                            </a>
                        </div>
                    </div>
                  </div>
                </div>
            <Footer />
            </div>
        </div>
    </div>
</template>

<script>
import Footer from '../components/Footer.vue';

export default {
    components: {
        Footer
    },
    props: {
        pokemon: {
            type: Object,
            required: true
        },
        detailsOpen: {
            type: Boolean,
            required: true
        },
        isScrolled: {
            type: Boolean,
            default: false
        }
    },
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
            if (customScrollbar) {
                customScrollbar.style.maxHeight = '100vh'; // Set max-height to 100% of viewport height
            }
        },
        handleCloseModal() {
            this.$emit('closeModal');
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
