<script setup lang="ts">
defineProps(["item"]);
</script>

<template>
  <div
    class="border col-span-1 border-gray-200 dark:border-gray-500 hover:border-primary-400 hover:border-solid dark:hover:border-primary-300 rounded relative group transition-all"
  >
    <NuxtImg
      v-if="item.cover"
      sizes="400px"
      :alt="`${item.title} banner`"
      class="w-full h-48 rounded-t object-cover"
      :src="item.cover ?? '/logo.png'"
    />
    <div
      v-else
      class="w-full h-48 flex justify-center items-center rounded-t font-bold text-2xl bg-gray-200 dark:bg-gray-600"
    >
      {{ item.title }}
    </div>
    <div class="p-6">
      <h3 class="m-0 text-lg font-semibold dark:text-gray-50">
        {{ item.title }}
      </h3>
      <p class="line-clamp-4 mt-2">
        {{ item.description }}
      </p>
      <div class="p-0 mt-2 flex gap-2">
        <UiTag v-for="tag in item.tags" :tag="tag" />
      </div>
      <div class="mt-2">
        <NuxtLink :to="item._path"> Leer todo </NuxtLink>
      </div>
    </div>
    
  </div>
</template>
