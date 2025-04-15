<script setup>
import Navbar from './components/Navbar.vue'
import Hero from "./components/Hero.vue";
import Service from "./components/Service.vue";
import Aboutsection from "./components/Aboutsection.vue";
import Testimonial from "./components/Testimonial.vue";
import Skill from "./components/Skill.vue";
import Project from "./components/Project.vue";
import Contact from "./components/Contact.vue";
import Backtop from "./components/Backtop.vue";
import Fotter from "./components/Fotter.vue";
</script>

<template>
  <div class="bg-[#111827] min-h-screen">
  <Navbar />
  <Hero/>
  <Service/>
  <Aboutsection/>
  <Skill/>
  <Project/>
  <Contact/>
  <Testimonial/>
  <Fotter/>
  <Backtop/>

    </div>
</template>

