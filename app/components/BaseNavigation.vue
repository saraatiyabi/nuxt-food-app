<script setup lang="ts"></script>

<template>
  <header class="py-4 border-b">
    <nav class="flex container items-center">
      <NuxtLink to="/" class="flex gap-1 items-center">
        <NuxtImg
          src="/icon-green.png"
          sizes="30px sm:35px md:45px"
          densities="x1"
          format="webp"
        />
        <span class="text-3xl font-bold">Nuxtcipes</span>
      </NuxtLink>
      <ul class="flex gap-6 ml-auto text-xl font-bold capitalize">
        <li>
          <NuxtLink to="/">Home</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/about">About Us</NuxtLink>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style scoped></style>
