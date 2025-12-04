<script setup lang="ts">
import { navList } from './config'
import { useRouter } from 'vue-router'

const router = useRouter()

function skip(url: string) {
  router.push(url)
}
</script>

<template>
  <div class="h-full header-container">
    <div class="p-0 navbar bg-base-100">
      <div class="navbar-start max-lg:w-full">
        <div class="dropdown">
          <label tabindex="0" class="btn btn-ghost lg:hidden">
            <svg
              xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" fill="none" viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="M4 6h16M4 12h8m-8 6h16"
              />
            </svg>
          </label>
          <ul
            tabindex="0"
            class="menu menu-sm dropdown-content mt-3 z-[1] p-2 shadow bg-base-100 rounded-box w-52 text-lg flex flex-col gap-2"
          >
            <li v-for="item in navList" :key="item.id" class="cursor-pointer hover:text-gray-100 hover:bg-base-200" @click="skip(item.url)">
              {{ item.name }}
            </li>
          </ul>
        </div>
        <a class="text-xl lg:pl-12 max-lg:mx-auto" href="https://vitejs.dev" target="_blank">
          <img src="/vite.svg" class="logo" alt="Vite logo">
        </a>
      </div>
      <div class="hidden navbar-center lg:flex">
        <ul class="flex gap-10 px-1 text-lg cursor-pointer menu menu-horizontal">
          <li v-for="item in navList" :key="item.id" class="hover:text-gray-100" @click="skip(item.url)">
            {{ item.name }}
          </li>
        </ul>
      </div>
      <div class="navbar-end max-lg:w-0">
        <button class="btn btn-ghost btn-circle btn-sm" aria-label="进入设置" @click="skip('/config')">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="w-5 h-5">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
              d="M12 15c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm6.5-3c0 .994-.344 1.907-.918 2.63l1.35 1.35-1.414 1.414-1.35-1.35A4.978 4.978 0 0 1 12 19a4.978 4.978 0 0 1-2.168-.434l-1.35 1.35-1.414-1.414 1.35-1.35A4.978 4.978 0 0 1 5 12c0-.994.344-1.907.918-2.63L4.568 8.02 5.982 6.606l1.35 1.35A4.978 4.978 0 0 1 12 5c.768 0 1.502.164 2.154.466l1.35-1.35 1.414 1.414-1.35 1.35c.574.723.918 1.637.918 2.63z"
            />
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss"></style>
