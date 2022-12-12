<script setup>
import Default from '~/layouts/default.vue'

const contentQuery = await queryContent('post/').sort(
  { timestamp: -1 }
).find()
</script>

<template>
  <default>
    <div class="flex flex-wrap -m-4">
      <div v-for="post in contentQuery" :key="post._id" class="p-2 md:w-1/3">
        <div class="h-full border-2 border-gray-200 border-opacity-60 rounded-lg overflow-hidden">
          <img
            class="lg:h-48 md:h-36 w-full object-cover object-center"
            :src="post.image"
            alt="blog image"
          >
          <div class="p-6">
            <h2 class="tracking-widest text-xs title-font font-medium text-gray-400 mb-1">
              {{ post.category }}
            </h2>
            <h1 class="title-font text-lg font-medium text-gray-900 mb-3">
              {{ post.title }}
            </h1>
            <p class="leading-relaxed mb-3">
              {{ post.description }}
            </p>
            <div class="flex items-center flex-wrap ">
              <NuxtLink :href="post._path" class="text-indigo-500 inline-flex items-center md:mb-2 lg:mb-0">
                Read More
                <Icon class="ml-1 pt-[1px]" name="heroicons-solid:arrow-right" size="1.1rem" />
              </NuxtLink>
              <span class="text-gray-400 mr-3 inline-flex items-center lg:ml-auto md:ml-0 ml-auto leading-none text-sm pr-3 py-1 border-r-2 border-gray-200">
                <Icon class="mr-1" name="heroicons-solid:eye" size="1.1rem" />
                1.2K
              </span>
              <span class="text-gray-400 inline-flex items-center leading-none text-sm">
                <Icon class="mr-1" name="heroicons-solid:heart" size="1.1rem" />
                6
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </default>
</template>
