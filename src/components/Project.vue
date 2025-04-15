<template>
    <section class="text-white mt-20" id="projects">
        <div class="px-4 xl:pl-16">
            <div class="mb-4 md:flex md:justify-between xl:pr-16">
                <h2 class="text-4xl font-bold text-white"> My Latest Projects</h2>
                <div class="flex space-x-4 mb-4 mt-5 md:mt-0">
                    <button class="hover:text-primary" v-for="category in ['all', 'web development', 'Mobile App']"
                        :key="category" @click="() => selectedCategory = category">
                        {{ category }}
                    </button>
                </div>
            </div>
            <ul class="px-4 sm:py-16 xl:pr-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3"
                data-aos="fade-right">
                <div v-for="project in filteredProjects" :key="project.id">
                    <div class="h-52 md:h-[12rem] rounded-t-xl relative group"
                    :style="{ backgroundImage: 'url(' + project.image + ')', backgroundSize: 'cover' }">                    
                    <div class="overlay items-center justify-center absolute top-0 left-0 w-full h-full bg-[#181818] bg-opacity-0
                    hidden group-hover:flex group-hover:bg-opacity-80 transition-all duration-500
                    ">
                        <a class="h-14 w-14 mr-2 border-2 relative rounded-full border-[#ADB7BE] hover:border-white group/link"
                            :href="project.webURL"> <svg xmlns="http://www.w3.org/2000/svg" fill="none"
                                viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true"
                                data-slot="icon"
                                class="h-10 w-10 text-[#ADB7BE] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2  cursor-pointer group-hover/link:text-white">
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M17.25 6.75 22.5 12l-5.25 5.25m-10.5 0L1.5 12l5.25-5.25m7.5-3-4.5 16.5">
                                </path>
                            </svg></a><a
                            class="h-14 w-14 border-2 relative rounded-full border-[#ADB7BE] hover:border-white group/link"
                            :href="project.gitURL"> <svg xmlns="http://www.w3.org/2000/svg" fill="none"
                                viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true"
                                data-slot="icon"
                                class="h-10 w-10 text-[#ADB7BE] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2  cursor-pointer group-hover/link:text-white">
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M2.036 12.322a1.012 1.012 0 0 1 0-.639C3.423 7.51 7.36 4.5 12 4.5c4.638 0 8.573 3.007 9.963 7.178.07.207.07.431 0 .639C20.577 16.49 16.64 19.5 12 19.5c-4.638 0-8.573-3.007-9.963-7.178Z">
                                </path>
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M15 12a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z"></path>
                            </svg></a>
                    </div>
                </div>
                <div class="text-white rounded-b-xl mt-3 bg-[#111a3e] shadow-lg border border-[#1f1641] py-6 px-4">
                    <h3 class="text-lg font-semibold uppercase lg:text-xl"> {{ project.title }}</h3>
                    <p class="text-[#ADB7BE]">{{ project.description }}</p>
                    <div class="flex flex-wrap p-2.5">
                        <div v-for="technology in project.technologies" :key="technology" class="text-center ml-1 mt-1 rounded-3xl bg-[#111827]"
                        style="box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1); border: 1px solid #111827;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);"
                        >
                    <p class="px-1 py-2">{{ technology }}</p>
                    </div>
                    </div>
                </div>
                </div>
            </ul>
        </div>
    </section>
</template>
<script setup>
import { ref, computed } from 'vue';

const Projects = ref([
    {
        id: 1,
        category: 'web development',
        image: 'src/assets/fetamovie.png',
        title: 'FetaFilms',
        description: 'A sleek Nuxt.js and Tailwind CSS project showcasing movies and TV series using the TMDB API. It features a responsive UI with dark/light mode, dynamic content display, interactive cards with routing, and global state management. Built with Vue 3, it highlights modern frontend skills, API integration, and responsive design—perfect for a portfolio project! 🚀',
        technologies: ['Nuxt-3', 'Tailwind', ],
        gitURL: 'https://github.com/johmik1997/cinema/tree/main',
        webURL: 'https://main--fetacinema.netlify.app/'
    },
    {
        id: 2,
        category: 'Mobile App',
        image: 'src/assets/mobile.jpg',
        title: 'Contact-Managment',
        description: 'A contact management system built with JavaFX and MySQL. It features a responsive UI with CRUD functionality, user authentication, and data (contact) storage ,update and also delete. Built with JavaFX, it showcases modern frontend skills, database integration, and responsive design—perfect for a portfolio project! 🚀',
        technologies: ['Javafx', 'css', 'Mysql'],
        gitURL: '',
        webURL: ''
    },
    {
        id: 3,
        category: 'web development',
        image: 'src/assets/Gebeya.png',
        title: 'E-commerce-Gebeya',
        description: 'A full-stack e-commerce project built with Nuxt.js, Tailwind CSS, Supabase, Stripe, and Prisma. It features a responsive UI with dark/light mode, user authentication, product listing, cart management, and checkout functionality. Built with Nuxt-3, it showcases modern frontend and backend skills, API integration, and responsive design—perfect for a portfolio project! 🚀',
        technologies: ['Nuxt-3', 'Tailwind', 'supabase','stripe','prisma'],
        gitURL: 'https://github.com/johmik1997/ecommerce/tree/main',
        webURL: 'https://ecommercegebeya.netlify.app/'
    },
    {
        id: 4,
        category: 'Web development',
        image: 'src/assets/peakcraft.png',
        title: 'project 1',
        description: 'PeakCraft is a dynamic and engaging website created for the club, designed to foster a community of creative individuals. Built with Vue and Tailwind CSS, the website offers a sleek and responsive user interface, making it easy for members to navigate, access club resources, and engage with various activities. The clean, modern design ensures a seamless experience, whether on desktop or mobile, while the performance-oriented architecture provides quick load times and smooth interactions.',
        technologies: ['vue.js 3', 'tailwind'],
        gitURL: 'https://github.com/johmik1997/peakcraft',
        webURL: 'https://peakcraftwebsite.onrender.com/'
    },
    {
        id: 5,
        category: 'web development',
        image: 'src/assets/quizapp.png',
        title: 'Quiz app',
        description: 'Quizapp is an interactive and user-friendly quiz app designed to help users test and improve their knowledge across various topics. With a wide range of quizzes on subjects like history, science, and pop culture, the app offers a fun and engaging way to challenge yourself. Its simple and intuitive interface allows users to easily navigate and track their performance, making it perfect for trivia enthusiasts, students, or anyone looking to learn while having fun. Whether you are looking to compete with friends or just enjoy a solo challenge, QuizMaster provides an exciting experience for all.',
        technologies: ['vue.js 3', 'css',],
        gitURL: 'https://github.com/johmik1997/quizapp',
        webURL: 'https://quizwebsite-forstudent.netlify.app/'
    },
    {
        id: 6,
        category: 'web development',
        image: 'src/assets/employee-portal.png',
        title: 'Employee-portal',
        description: "A robust and user-friendly web application designed to streamline employee and event management within an organization. The system features secure authentication for both admins and regular users.Admins have full control with capabilities to add, view, update, and delete employee records. They can also manage team assignments and post upcoming events and announcements for the organization.Regular users can log in to the portal to view their team members, stay updated with upcoming events, and read important announcements, creating a connected and informed workplace environment.",
        technologies: ['vue.js 3', 'css','Go(Golang)','axios','postgresql'],
        gitURL: 'https://github.com/johmik1997/frontendvue-with-gobackend',
        webURL: 'https://frontendvue-with-gobackend.onrender.com/'
    },
   
]);

const selectedCategory = ref('all');
const filteredProjects = computed(() => {
    if (selectedCategory.value === 'all') {
        return Projects.value;
    }
    return Projects.value.filter(project => project.category.toLocaleLowerCase() === selectedCategory.value.toLocaleLowerCase());
})

</script>
