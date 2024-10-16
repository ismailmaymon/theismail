<template>
  <div class="">
    <!-- Desktop header -->
    <div class="sm:block hidden">
      <header
        class="h-[80px] flex justify-between px-6 items-center bg-white shadow z-50 right-[7px] fixed w-full transition-padding duration-500 ease-in-out">
        <a href="">
          <div class="flex items-center cursor-pointer gap-4">

            <img src="../assets//ismail.jpg" alt=""
              class="rounded-full object-cover transition-padding duration-500 ease-in-out"
              :class="{ 'h-12 w-12': isScrolled, 'h-[58px] w-[58px]': !isScrolled }">

            <label class="text-xl text-blue-950 font-medium cursor-pointer">Ismail Memon</label>
          </div>
        </a>
        <div class="flex gap-5">
          <a href="#home">
            <h4 class="font-normal text-lg cursor-pointer header-effect text-blue-950">Home</h4>
          </a>
          <a href="#about">
            <h4 class="font-normal text-lg cursor-pointer header-effect text-blue-950">About</h4>
          </a>
          <a href="#projects">
            <h4 class="font-normal text-lg cursor-pointer header-effect text-blue-950">Projects</h4>
          </a>
        </div>
      </header>
    </div>

    <!-- Mobile header -->
    <div class="sm:hidden block">
      <header 
        class="h-[77px] flex justify-between px-5 py-3 items-center bg-white shadow z-50 fixed w-full transition-padding duration-500 ease-in-out">
        <a href="">
          <div class="flex items-center gap-3 cursor-pointer">
            <img src="../assets//ismail.jpg" alt=""
              class="rounded-full object-cover transition-padding duration-500 ease-in-out"
              :class="{ 'h-12 w-12': isScrolled, 'h-14 w-14': !isScrolled }">
            <label class="text-xl text-blue-950 font-medium cursor-pointer">Ismail Memon</label>
          </div>
        </a>
        <div class="flex items-center gap-3">
          <!-- Menu bar button -->
          <button @click="toggleMenu">
            <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-menu-2"
              width="24" height="24" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" fill="none"
              stroke-linecap="round" stroke-linejoin="round">
              <path stroke="none" d="M0 0h24v24H0z" fill="none" />
              <path d="M4 6l16 0" />
              <path d="M4 12l16 0" />
              <path d="M4 18l16 0" />
            </svg>
          </button>
        </div>
      </header>

      <!-- Mobile Menu Modal -->
      <div v-if="isMenuOpen" class="fixed right-[20px] top-16 z-[1000] flex justify-center items-center">
        <div class="bg-white w-48 rounded-lg shadow">

          <!-- Menu content -->
          <ul class="w-full">
            <a href="#home"><li @click="closeMenu" class="text-gray-700 rounded-t-lg hover:bg-gray-100 px-6 py-2 w-full hover:text-gray-900">Home</li></a>
            <a href="#about"><li @click="closeMenu" class="text-gray-700 hover:bg-gray-100 px-6 py-2 w-full hover:text-gray-900">About</li></a>
            <a href="#projects"><li @click="closeMenu" class="text-gray-700 rounded-b-lg hover:bg-gray-100 px-6 py-2 w-full hover:text-gray-900">Projects</li></a>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
    
      isMenuOpen: false
    };
  },

  methods: {

    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    closeMenu() {
      this.isMenuOpen = false;
    }
  }
};
</script>

<style>
/* Add any additional styles here */
</style>