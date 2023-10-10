<script setup>
  import { ref } from 'vue'
  import { RouterLink, RouterView } from 'vue-router';
  import MenuItem from './components/MenuItem.vue';

  //icons to be used
  import ChevronUp from 'vue-material-design-icons/ChevronUp.vue';
  import ChevronDown from 'vue-material-design-icons/ChevronDown.vue';
  import ChevronLeft from 'vue-material-design-icons/ChevronLeft.vue';
  import ChevronRight from 'vue-material-design-icons/ChevronRight.vue';

  let openMenu = ref(false)
</script>

<template>
  <div>
    <div class="
      w-[calc(100%-240px)]
      h-[60px]
      fixed
      right-0
      z-20
      bg-[#101010]
      bg-opacity-80
      flex
      items-center
      justify-between
      "
    >
      <div class="flex items-center ml-6 gap-2">
        <button type="button" class="rounded-full bg-black p-[1px] cursor-pointer">
          <ChevronLeft fillColor="#FFFFFF" :size="30"/>
        </button>
        <button type="button" class="rounded-full bg-black p-[1px] cursor-pointer">
          <ChevronRight fillColor="#FFFFFF" :size="30"/>
        </button>
      </div>
      <button @click="openMenu = !openMenu" :class="openMenu ? 'bg-[#282828]' : 'bg-black'" class="bg-black hover:bg-[#282828] rounded-full p-0.5 mr-8 mt-0,5 cursor-pointer ">
        <div class="flex items-center">
          <img class="rounded-full" width="27" src="https://yt3.ggpht.com/yti/ADpuP3N8StFxD9Y7J3bplfySaal6sxYVIoVOg3w6pYrAoA=s88-c-k-c0x00ffffff-no-rj"/>
          <p class="text-white text-[14px] ml-1.5 font-semibold">Sebastian Flores</p>
          <ChevronDown v-if="!openMenu" @click="openMenu = true" fillColor="#FFFFFF" :size="25"/>
          <ChevronUp v-else @click="openMenu = false" fillColor="#FFFFFF" :size="25"/>
        </div>
      </button>
      <span v-if="openMenu"
      class="fixed w-[190px] bg-[#282828] shadow-2xl z-50 rounded-sm top-[52px] right-[35px] p-1 cursor-pointer">
        <ul class="text-gray-200 font-semibold text-[14px]">
          <li class="px-3 py-2.5 hover:bg-[#3E3D3D]  ">Account</li>
        </ul>
        <ul class="text-gray-200 font-semibold text-[14px]">
          <li class="px-3 py-2.5 hover:bg-[#3E3D3D]  ">Manage Plan</li>
        </ul>
        <ul class="text-gray-200 font-semibold text-[14px]">
          <li class="px-3 py-2.5 hover:bg-[#3E3D3D]  ">Profile</li>
        </ul>
        <ul class="text-gray-200 font-semibold text-[14px]">
          <li class="px-3 py-2.5 hover:bg-[#3E3D3D] ">Private session</li>
        </ul>
        <ul class="text-gray-200 font-semibold text-[14px]">
          <li class="px-3 py-2.5 hover:bg-[#3E3D3D] border-b border-b-gray-600">Preference</li>
        </ul>
        <ul class="text-gray-200 font-semibold text-[14px]">
          <li class="px-3 py-2.5 hover:bg-[#3E3D3D] border-b border-b-gray-600">Log out</li>
        </ul>
      </span>
    </div>
    <div
      id="SideNav"
      class="h-[100%] p-6 w-[240px] fixed z-50 bg-black"
    >
      <RouterLink to="/">
        <img width="125" src="/images/icons/spotify-logo.png"/>
      </RouterLink>
      <div class="my-8"></div>
      <ul>
        <RouterLink to="/">
          <MenuItem class="ml-[1px]" :iconSize="23" name="Home" iconString="home" pageUrl="/"/>
        </RouterLink>
        <RouterLink to="/search">
          <MenuItem class="ml-[1px]" :iconSize="24" name="Search" iconString="search" pageUrl="/search"/>
        </RouterLink>
        <RouterLink to="/library">
          <MenuItem class="ml-[2px]" :iconSize="23" name="Library" iconString="library" pageUrl="/library"/>
        </RouterLink>
        <div class="py-3.5"/>
        <MenuItem :iconSize="24" name="Create Playlist" iconString="playlist" pageUrl="/playlist"/>
        <MenuItem class="-ml-[1px]" :iconSize="27" name="Liked Songs" iconString="liked" pageUrl="/liked"/>
      </ul>
      <div class="border-b border-b-gray-700"/>
      <ul>
        <li class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white">Playlist #1</li>
        <li class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white">Playlist #2</li>
        <li class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white">Playlist #3</li>
        <li class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white">Playlist #4</li>
      </ul>
    </div>
  </div>
  
  <div
    class="fixed right-0 top-0 w-[calc(100%-240px)] h-full bg-gradient-to-b from-[#1C1C1C] to-black "
  >

  </div>
</template>

