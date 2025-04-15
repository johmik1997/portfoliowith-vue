<template >
    <section class="text-white mt-20" id="testimonials" data-aos="zoom-in">
        <h2 class="text-4xl font-bold text-white text-left mb-4 px-4 xl:pl-16">Testimonials</h2>
        <div class="px-4 xl:px-16">
            <Carousel v-bind="settings" :breakpoints="breakpoints" >
                <Slide v-for="element in testimonials" :key="element.id">
                    <div class="carousel__item p-4">
                        <div class="w-full mx-auto bg-[#111a3e] shadow-lg border border-[#1f1641] p-5 text-white font-light mb-6">
                            <div class="w-full flex mb-4 items-center">
                                <div class="overflow-hidden rounded-full w-10 h-10 bg-gray-50 border border-gray-200">
                                    <img :src="element.image" alt="testimonial image" loading="lazy">
                                </div>
                                <h6 class="ml-4 font-bold text-sm uppercase text-white">{{ element.fullName }}</h6>
                            </div>
                            <div class="w-full">
                                <p class="text-sm leading-tight">
                                    <span class="text-lg leading-none italic font-bold text-white mr-1">"</span>
                                        {{ element.comment }}
                                    <span class="text-lg leading-none italic font-bold text-white mr-1">"</span>
                                </p>
                            </div>
                        </div>
                    </div>
                </Slide> 
                <template #addons>
                    <Navigation />
                </template>
            </Carousel>
        </div>
    </section>
</template>
<script setup>
import { ref } from 'vue';
import { Carousel , Navigation , Slide } from 'vue3-carousel';
import 'vue3-carousel/dist/carousel.css';
//Carousel settings
const settings =ref({
    itemsToShow:1,
    snapAlign:"center",
})

//Breakpoints
const breakpoints =ref({
    700:{
        itemsToShow:2.5,
        snapAlign:'center',
    },
    1024:{
        itemsToShow:3,
        snapAlign:'start'
    }
})

const testimonials=ref([
    {
        id:1,
        fullName:'sarah',
        image:'https://randomuser.me/api/portraits/women/40.jpg',
        comment:"The employee portal is super intuitive and makes team and task management effortless. Really impressed with the UX and functionality!"
    },
    {
        id:2,
        fullName:'john barry',
        image:'https://randomuser.me/api/portraits/men/40.jpg',
        comment:"Fetafim offers a smooth movie browsing experience with clean API integration and a slick interface. It’s fast and fun to use!"   },
    {
        id:3,
        fullName:'lucas',
        image:'https://randomuser.me/api/portraits/men/41.jpg',
        comment:"The contact management system is well-organized, responsive, and user-friendly—perfect for staying on top of important connections."  },
    {
        id:4,
        fullName:'maria',
        image:'https://randomuser.me/api/portraits/women/45.jpg',
        comment:"The quiz app is engaging, fast, and easy to navigate. Great for learning or just testing your knowledge on the go!"   },
    {
        id:5,
        fullName:'angelina',
        image:'https://randomuser.me/api/portraits/women/30.jpg',
        comment:"PeakCraft’s club website looks amazing—modern, responsive, and a perfect showcase of the club’s vibe and events!"  },
])
</script>
<style >
    .carousel__prev,.carousel__next {
        color: white !important;
    }
</style>