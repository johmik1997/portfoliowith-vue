<template >
    <section class="text-white mt-20" id="services">
        <div class="px-4 xl:pl-16">
            <h2 class="text-4xl font-bold text-white mb-4">My Services</h2>
        </div>
        <div class="py-8 xl:px-16 px-4 sm:py-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3">
            <div v-for="service in services" :key="service.id" data-aos="fade-up"
            class="px-8 py-12 rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641]"
            >
                <div class="mx-auto h-24 w-24 text-center xl:h-28 xl:w-28">
                    <div>
                        <img :src="service.icon" alt="service icon">
                    </div>
                </div>
                <div class="text-center">
                    <h3 class="pt-8 text-lg font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary lg:text-xl">
                        {{ service.name }}
                    </h3>
                    <p class="text-grey pt-4 text-sm group-hover:text-white md:text-base">
                        {{ service.description }}
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>
<script setup>
import { ref } from 'vue';

const services = ref([
    {
        id: 1,
        icon: 'https://img.icons8.com/ios-filled/100/ffffff/google-code.png',
        name: 'WEB DEVELOPMENT',
        description: "i am  full stack developer i have made many websites mostly for personal,with react but i passionated in nuxt-3 "},
    {
        id: 2,
        icon: 'https://img.icons8.com/external-vectorslab-glyph-vectorslab/100/fffeee/external-Technical-Writing-mobile-app-development-vectorslab-glyph-vectorslab.png',
        name: 'software engineer',
        description: 'I am also working with preparing the documentation for sotware development like i am doing for pharmacy managment system,it has many diagrams including usecase,sequential...'
    },
    {
        id: 3,
        icon: 'https://img.icons8.com/ios-filled/100/ffffff/email-open.png',
        name: 'Mobile Development',
        description: "i am also more passionated in mobile development ,i am work with javafx more recent java GUI but i am learning flutter to develop my proffesion"    },
    {
        id: 4,
        icon: 'https://img.icons8.com/ios-filled/100/ffffff/google-code.png',
        name: 'WEB DEVELOPMENT',
        description: 'I worked using vue,Tailwind Peakcraft website. peakcraft is our campus club that helps to gain the soft skills for tech passionated students '
    },
    {
        id: 5,
        icon: 'https://img.icons8.com/ios-filled/100/ffffff/windows10-personalization.png',
        name: 'Graphic Design',
        description: 'i am tring to work graphic design i have taken graphics course previously, currently i am not active but i have done for my web design in addition to Figma '
    },
    {
        id: 6,
        icon: 'https://img.icons8.com/ios-filled/100/ffffff/web-design.png',
        name: 'Web Design',
        description: 'i am not active but i have a little experiance with Figma'
    },
]);
</script>