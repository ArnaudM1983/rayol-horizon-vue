<template>
    <header>
        <div class="flex justify-between items-center p-8 lg:px-12 relative z-20">
            <div class="text-3xl text-red-500">LOGO</div>

            <!-- Mobile Toggle Button-->
             <div class="md:hidden z-30">
                <button class="block focus:outline-none" @click="isMenuOpen = !isMenuOpen">
                    <span v-if="isMenuOpen" class="text-5xl text-red-500">
                        <Icon icon="material-symbols:close"/>
                    </span>
                    <span v-else class="text-5xl text-red-500">
                        <Icon icon="material-symbols:menu"/>
                    </span>
                </button>
             </div>

             <!-- Navbar Link s-->

        </div>
    </header>
</template>
<script setup>
import { ref } from "vue";
const isMenuOpen = ref(false);

</script>
