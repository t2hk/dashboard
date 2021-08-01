<template>
<div class="text-gray-600 body-font">
  <div class="container mx-auto flex flex-wrap p-5 flex-col md:flex-row items-center">
    <a class="flex title-font font-medium items-center text-gray-900 mb-4 md:mb-0">
      <span class="ml-3 text-xl">Header Menu</span>
    </a>
    <nav class="md:ml-auto flex flex-wrap items-center text-base justify-center">
      <a class="mr-5 hover:text-gray-900">First Link</a>
      <a class="mr-5 hover:text-gray-900">Second Link</a>
      <a class="mr-5 hover:text-gray-900">Third Link</a>
      <a class="mr-5 hover:text-gray-900">Fourth Link</a>
    </nav>
    <button class="btn btn-blue">Button</button>
  </div>
  </div>
</template>

<script>
</script>

<style>
.btn {
  @apply font-bold py-2 px-4 rounded;
}
.btn-blue {
  @apply bg-blue-500 text-white;
}
.btn-blue:hover {
  @apply bg-blue-700;
}
</style>
