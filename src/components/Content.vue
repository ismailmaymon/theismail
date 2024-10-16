<template>
    <div class="">
        <Header />
        <div>
            <div id="home" class="background-image py-20 sm:py-32 sm:px-0 px-5 ">
                <div class="sm:max-w-3xl mx-auto sm:pt-24 pt-[70px]">
                    <h1 class="text-white text-4xl sm:text-6xl sm:leading-[70px] text-center">Hey, My name is Ismail
                        Memon
                    </h1>
                    <p class="text-center text-white pt-4 sm:text-lg">
                        I use React, Vue, and CSS to build my website. Leveraging React and Vue for their versatility in
                        developing modern web applications, I ensure a modular and scalable project structure. CSS is
                        then
                        employed to create visually appealing and responsive web pages, enhancing the overall user
                        experience.
                    </p>
                    <div class="flex justify-center mt-7">
                        <a href="#projects">
                            <button
                                class="bg-white text-blue-950 px-10 py-2 rounded-lg font-medium shadow text-lg transition ease-in-out duration-300 transform button">Projects</button>
                        </a>
                    </div>
                </div>
            </div>
            <div class="container mx-auto">
                <div class="pt-20 sm:pt-24 sm:px-10 px-5" id="about">
                    <div class="sm:max-w-3xl mx-auto">
                        <h4 class="text-blue-950 text-center text-3xl sm:text-4xl">About Me</h4>
                        <div class="bg-blue-950 rounded-full w-10 h-2 shadow sm:my-4 my-3 mx-auto"></div>
                        <p class="text-center">
                            I use React, Vue, and CSS to build my website. Leveraging React and Vue for their
                            versatility in
                            developing modern web applications, I ensure a modular and scalable project structure. CSS
                            is
                            then
                            employed to create visually appealing and responsive web pages, enhancing the overall user
                            experience.
                        </p>
                    </div>
                    <div class=" mt-16 sm:flex sm:justify-between sm:gap-8">
                        <div class="sm:max-w-xl w-full">
                            <h2 class="text-blue-950 text-xl">SPECIALIZATIONS</h2>
                            <p class="mt-3">
                                Front-End Crafting (HTML, CSS, Figma, Sass)
                                Passionate about TailwindCSS (♥)
                                JavaScript ES6/*7 (Data Modeling, Debugging, Asynchronous Execution)
                                Front-End Mastery (Vue.js, React.js, Svelte)
                                User Interface/User Experience Design
                                Creative Problem-Solving using Design Thinking
                                Skilled in developing high-performing front-end interfaces with seamless backend API
                                interactions.
                            </p>
                        </div>
                        <div class="sm:max-w-xl w-full sm:mt-0 mt-10">
                            <h2 class="text-blue-950 text-xl">My Skills</h2>
                            <div class="flex flex-wrap sm:gap-4 gap-3 mt-4">
                                <div v-for="(skill, index) in skills" :key="index"
                                    class="bg-blue-950 rounded text-white sm:px-3 px-2 sm:text-lg py-1">
                                    {{ skill }}
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="pt-20 sm:pt-24 sm:px-10 px-5" id="projects">
                    <div class="max-w-3xl mx-auto">
                        <h4 class="text-blue-950 text-center text-3xl sm:text-4xl">Projects</h4>
                        <div class="bg-blue-950 rounded-full w-10 h-2 shadow sm:my-4 my-3 mx-auto"></div>
                        <p class="text-center">
                            These are my portfolio projects
                        </p>
                    </div>
                    <div v-for="item in (key, projects)" class="mt-12 w-full sm:flex gap-10">
                        <div class="sm:w-6/12">
                            <img :src="item.imageUrl" alt=""
                                class="sm:p-10 p-2 w-full object-contain shadow bg-blue-950 rounded">
                        </div>
                        <div class="sm:w-6/12 sm:mt-0 mt-8">
                            <h2 class="text-2xl">{{ item.title }}</h2>
                            <p class="mt-1">{{ item.overview }}</p>
                            <button @click="HandleCaseStudy(item)"
                                class="sm:mt-20 mt-8 bg-blue-950 text-white px-4 py-2 rounded-lg button text-lg">Case
                                Study</button>
                        </div>
                    </div>
                    <div v-if="detailsOpen === true">
                        <Detail :detailsOpen="detailsOpen" @closeModal="detailsOpen = false" :pokemon="pokemon" />
                    </div>
                </div>
            </div>
        </div>

        <Footer />
    </div>
</template>
<script>
import Footer from '../components/Footer.vue';
import pokemonImage from '../assets//pokemon-project.png'
import todoListImage from '../assets/todo-list.png'
import Detail from '../pages/Detail.vue'
import Header from '../components/Header.vue';

export default {
    components: {
        Detail,
        Header,
        Footer
    },
    data() {
        return {
            detailsOpen: false,
            pokemon: {},
            skills: ['HTML', 'CSS', 'JavaScript', 'Vue Js', 'React Js', 'Saas', 'Git', 'Shopify', 'Nuxt Js', 'Expo Js'],
            projects: [
                {
                    usesLanguage: ["Vue", "CSS", "JavaScript", "HTML"],
                    title: "Pokemon",
                    overview: "I was a kid during the 90s when Pokemon was at it's peak and virtually every child was obsessed with it. Now, 22 years later, most of those chil dren have grown out of it, but I never did. It's a franchise whose primary audience is children, so what do you see in it that keeps you interested as an adult?",
                    imageUrl: pokemonImage,
                    liveLink: "https://pokemon-pro-web.netlify.app/",
                    githubLink: "https://github.com/theismailmemon/pokemon"
                },
                {
                    usesLanguage: ["Vue", "CSS", "JavaScript", "HTML"],
                    title: "Todo List",
                    overview: "To prepare for the day, start with some morning yoga or stretching. Get ready for any important meetings or appointments. Prepare your meals for the day and focus on completing an important task. Take a break in the afternoon to relax before diving back into work.",
                    imageUrl: todoListImage,
                    liveLink: "https://todo-list-pro-web.netlify.app/",
                    githubLink: "https://github.com/theismailmemon/todo-list"
                },
            ]
        }
    },
    methods: {
        HandleCaseStudy(item) {
            this.pokemon = item
            this.detailsOpen = true
        }
    }
}
</script>
<style>
.socialLinks:hover {
    transform: scale(1.2);
    /* Increase the size on hover */
}

.socialLinks {
    transition: transform 0.3s ease-in-out;
    /* Add smooth transition */
}

.button:hover {
    transform: scale(1.1);
    /* Increase the size on hover */
}

.button {
    transition: transform 0.3s ease-in-out;
    /* Add smooth transition */
}


.background-image {
    background-image: url('https://wallpapercave.com/wp/wp2446126.jpg');
    background-size: cover;
    /* Adjust to your preference */
    background-position: center;
    /* Adjust to your preference */
    background-repeat: no-repeat;
}

.header-effect {
    display: inline-block;
    padding-left: 10px;
    padding-right: 10px;
    padding-top: 8px;
    padding-bottom: 8px;
    text-decoration: none;

    /* Header color */
    position: relative;
}

.header-effect::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 2px;
    bottom: 0;
    left: 0;
    background-color: #001f3f;
    /* Underline color */
    transform: scaleX(0);
    transform-origin: bottom right;
    transition: transform 0.3s ease-out;
}

.header-effect:hover::before {
    transform: scaleX(1);
    transform-origin: bottom left;
}
</style>