<template>
    <footer class="bg-blue-950 mt-10 sm:py-10 py-5 sm:px-0 px-3 ">

        <div class="flex justify-center items-center gap-8">
            <template v-for="social in socialLinks" :key="social.href">
                <a :href="social.href" target="_blank" rel="noopener noreferrer" class="socialLinks">
                    <svg xmlns="http://www.w3.org/2000/svg"
                        class="sm:h-10 h-8 sm:w-10 w-8 cursor-pointer transition ease-in-out duration-300 icon icon-tabler"
                        viewBox="0 0 24 24" stroke-width="1.5" stroke="#ffffff" fill="none" stroke-linecap="round"
                        stroke-linejoin="round">
                        <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                        <path :d="social.path" />
                    </svg>
                </a>
            </template>
        </div>
        <div class="mt-5">
            <p class="text-sm text-center text-white">Connect with me on social media and let's create something awesome
                together!</p>
        </div>
        <div class="mt-6">
            <p class="text-sm text-center text-white">Copyright © {{ new Date().getFullYear() }} Ismail Memon. All rights
                reserved.</p>
        </div>
    </footer>
</template>
<script>
export default {
    data() {
        return {
            socialLinks: [
                {
                    href: "https://www.linkedin.com/in/ismail-memon-5a36b32b8/",
                    path: "M4 4m0 2a2 2 0 0 1 2 -2h12a2 2 0 0 1 2 2v12a2 2 0 0 1 -2 2h-12a2 2 0 0 1 -2 -2z M8 11l0 5 M8 8l0 .01 M12 16l0 -5 M16 16v-3a2 2 0 0 0 -4 0"
                },
                {
                    href: "https://github.com/ismailmaymon",
                    path: "M9 19c-4.3 1.4 -4.3 -2.5 -6 -3m12 5v-3.5c0 -1 .1 -1.4 -.5 -2c2.8 -.3 5.5 -1.4 5.5 -6a4.6 4.6 0 0 0 -1.3 -3.2a4.2 4.2 0 0 0 -.1 -3.2s-1.1 -.3 -3.5 1.3a12.3 12.3 0 0 0 -6.2 0c-2.4 -1.6 -3.5 -1.3 -3.5 -1.3a4.2 4.2 0 0 0 -.1 3.2a4.6 4.6 0 0 0 -1.3 3.2c0 4.6 2.7 5.7 5.5 6c-.6 .6 -.6 1.2 -.5 2v3.5"
                },
                {
                    href: "https://wa.me/923183122754",
                    path: "M3 21l1.65 -3.8a9 9 0 1 1 3.4 2.9l-5.05 .9 M9 10a.5 .5 0 0 0 1 0v-1a.5 .5 0 0 0 -1 0v1a5 5 0 0 0 5 5h1a.5 .5 0 0 0 0 -1h-1a.5 .5 0 0 0 0 1"
                },
                {
                    href: "mailto:theismailmemon@gmail.com",
                    path: "M16 20h3a1 1 0 0 0 1 -1v-14a1 1 0 0 0 -1 -1h-3v16z M5 20h3v-16h-3a1 1 0 0 0 -1 1v14a1 1 0 0 0 1 1z M16 4l-4 4l-4 -4 M4 6.5l8 7.5l8 -7.5"
                }
            ]
        };
    },
}
</script>

