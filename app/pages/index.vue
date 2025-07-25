<script setup lang="ts">
import { type RecipesResponse } from "./../../types/types";
// const { data, error } = await useAsyncData("recipes", () =>
//   $fetch("https://dummyjson.com/recipes?limit=12")
// );

const { data, status, error } = await useFetch<RecipesResponse>(
  "https://dummyjson.com/recipes?limit=12"
);

useSeoMeta({
  title: "Nuxtcipes",
  description: "Recipes for you to cook!",
  ogTitle: "Nuxtcipes",
  ogDescription: "Recipes for you to cook!",
  ogImage: "/nuxt-course-hero.png",
  ogUrl: `http:localhost:3000`,
  twitterTitle: "Nuxtcipes",
  twitterDescription: "Recipes for you to cook!",
  twitterImage: "/nuxt-course-hero.png",
  twitterCard: "summary",
});

useHead({
  htmlAttrs: {
    lang: "en",
  },
  link: [
    {
      rel: "icon",
      type: "image/png",
      href: "/favicon.png",
    },
  ],
});
</script>

<template>
  <div>
    <main>
      <section class="bg-[#f1f1f1]">
        <div
          class="container flex flex-col lg:flex-row items-center py-20 gap-10"
        >
          <div class="flex-1 order-2 lg:order-1 text-center lg:text-left">
            <h1 class="text-4xl lg:text-6xl font-extrabold mb-6 text-balance">
              Master the Kitchen with Ease: Unleash Your Inner Chef Today!
            </h1>
            <p class="text-xl lg:text-2xl mb-8 text-balance">
              Discover recipes helping you to find the easiest way to cook.
            </p>
            <button
              class="px-4 py-2 text-white self-start bg-dodgeroll-gold-400 rounded-md text-lg cursor-pointer"
            >
              Browse Recipes
            </button>
          </div>
          <div class="flex-1 order-1 lg:order-2">
            <NuxtImg
              src="/nuxt-course-hero.png"
              alt=""
              densities="x1"
              sizes="100vw xs:75vw sm:50vw md:500px"
            />
          </div>
        </div>
      </section>
      <section class="py-20 container">
        <h2 class="text-3xl lg:text-5xl mb-2">Discover, Create, Share</h2>
        <p class="text-lg lg:text-xl mb-8">
          Check out our most popular recipes!
        </p>
        <div
          v-if="!error"
          class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-x-4 gap-y-8"
        >
          <div v-for="recipe in data?.recipes">
            <Recipe :recipe="recipe" />
          </div>
        </div>
        <p class="text-md" v-else>
          OOPs something went wrong while loading recipes! please try again in a
          while!
        </p>
      </section>
    </main>
  </div>
</template>

<style scoped></style>
