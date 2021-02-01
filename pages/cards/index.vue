<template>
  <div class="container px-6 mx-auto grid dark:bg-gray-800">
    <h2
      class="my-6 text-2xl font-semibold text-gray-700 dark:text-gray-200 dark:text-white"
    >
      Card
    </h2>
    <h1 class="text-gray-900 dark:text-white">Dark mode is here!</h1>
    <p class="text-gray-600 dark:text-gray-300">Lorem ipsum...</p>

    <div class="bg-white dark:bg-gray-800">
      <h1 class="text-gray-900 dark:text-white">Dark mode is here!</h1>
      <p class="text-gray-600 dark:text-gray-300">Lorem ipsum...</p>
    </div>

    <div class="max-w-md mx-auto bg-white rounded-xl shadow-md overflow-hidden md:max-w-2xl">
  <div class="md:flex">
    <div class="md:flex-shrink-0">
      <img class="h-48 w-full object-cover md:w-48" src="~/assets/img/create-account-office.jpeg" alt="Man looking at item at a store">
    </div>
    <div class="p-8">
      <div class="uppercase tracking-wide text-sm text-indigo-500 font-semibold">Case study</div>
      <a href="#" class="block mt-1 text-lg leading-tight font-medium text-black hover:underline">Finding customers for your new business</a>
      <p class="mt-2 text-gray-500">Getting a new business off the ground is a lot of hard work. Here are five ideas you can use to find your first customers.</p>
    </div>
  </div>
</div>
  </div>
</template>
<script>
export default {
  layout: "dashboard",
};
</script>

<style scoped>
</style>