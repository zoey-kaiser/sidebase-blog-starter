<template>
  <div class="min-h-[100vh] dark:bg-gray-900 dark:text-white">
    <div class="container mx-auto py-10 px-8">
      <nav class="flex items-center justify-between border-b-2 pb-5">
        <div>
          <h1 class="text-5xl font-bold">
            Blog Starter
          </h1>
          <h3 class="text-2xl font-light">
            built with <NuxtLink class="text-blue-500 underline" href="https://sidebase.io" target="_blank">sidebase.io</NuxtLink>
          </h3>
        </div>
        <div class="hidden justify-between items-center w-full lg:flex lg:w-auto lg:order-1">
          <ul class="flex flex-col mt-4 font-medium lg:flex-row lg:space-x-8 lg:mt-0">
            <li>
              <NuxtLink href="/" class="block py-2 pr-4 pl-3 text-gray-700 border-b border-gray-100 hover:bg-gray-50 lg:hover:bg-transparent lg:border-0 lg:hover:text-blue-500 lg:p-0 dark:text-gray-400 lg:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white lg:dark:hover:bg-transparent dark:border-gray-700">
                Home
              </NuxtLink>
            </li>
          </ul>
        </div>
      </nav>
      <main class="pt-10">
        <slot />
      </main>
    </div>
  </div>
</template>
