<script setup>
const { page } = useContent()
</script>

<template>
  <main>
    <NuxtLink href="/">
      <Icon name="heroicons-solid:arrow-left" />
      Back
    </NuxtLink>
    <header class="flex items-center justify-between mb-4 lg:mb-6 not-format">
      <div class="w-full">
        <div class="mb-4">
          <p class="font-light text-gray-500 dark:text-gray-400 text-md">
            Published on <FormatDate :date="new Date(page.timestamp * 1000)" />
          </p>
          <h1 class="text-2xl font-extrabold leading-tight lg:mb-6 lg:text-4xl text-gray-900 dark:text-white">
            {{ page.title }}
          </h1>
        </div>
        <address class="flex items-center not-italic w-full">
          <div class="flex items-center mr-3 text-sm text-gray-900 dark:text-white w-full">
            <NuxtLink :href="page.avatarLink" target="_blank">
              <img class="mr-4 w-12 h-12 rounded-full" :src="page.authorAvatar" :alt="page.author">
            </NuxtLink>
            <div class="flex items-end justify-between w-full ml-2">
              <NuxtLink :href="page.avatarLink" target="_blank">
                <span rel="author" class="text-base font-bold text-gray-900 dark:text-white">
                  {{ page.author }}
                </span>
                <p class="text-sm font-light text-gray-500 dark:text-gray-400">
                  {{ page.position }}
                </p>
              </NuxtLink>
            </div>
          </div>
        </address>
      </div>
    </header>
    <div class="prose">
      <ContentDoc />
    </div>
  </main>
</template>
