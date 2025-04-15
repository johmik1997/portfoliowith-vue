<template>

        <nav class="flex justify-between items-center p-6 bg-opacity-50 relative z-20">
            <div class="hover:text-teal-400 hover:shadow-red-300 text-lg"><a href="/"><h1 class="text-orange-500  hover:shadow  hover:text-green-300">YOHA <span class="text-orange-300 hover:text-red-950" >NNES</span></h1></a>
        
        </div>
        <div class="md:hidden z-30"><button class="block focus:outline-none"  @click="mobileview=!mobileview">
            <span v-if="mobileview" class="text-5xl">
                <img src="https://img.icons8.com/ios-filled/100/ffffff/delete-sign.png" alt="close" width="50" height="50">
            </span>
            <span v-else class="text-5xl">
                <img src="https://img.icons8.com/ios-filled/100/ffffff/menu--v6.png" alt="menu" width="50" height="50">
            </span>
        </button></div>
    
        <div :class="['fixed inset-0 z-20 flex flex-col items-center justify-center bg-[#111827] md:relative md:bg-transparent md:flex md:justify-between md:flex-row',
            mobileview ? 'block':'hidden'
          ]">
            <ul class="flex flex-col items-center space-y-5 md:flex-row md:space-x-5 md:space-y-0" >
                <li v-for="items in menus"><a class="block text-white transition hover:text-primary ease-linear text-2xl md:text-white md:text-lg" :href="items.link" :key="items.name">{{ items.name }}</a></li>
            </ul>
        </div>
        </nav>
   
</template>

<script setup>
import { RouterLink } from 'vue-router';
import {ref} from 'vue'
const mobileview=ref(false)
const menus=ref([
    {name:'service',
     link:'#service'
    },
    {name:'About',
     link:'#about'
    },
    {name:'Skill',
     link:'#skill'
    },
    {name:'Project',
     link:'#project'
    },
    {name:'Contact',
     link:'#contact'
    }
])
</script>

