<script setup lang="ts">
const { data } = await useAsyncData('blog', () => queryContent('/blog').where({ _path: { $ne: "/blog" }, _extension: "md" }).find());
</script>

<template>
  <div class=" grid grid-cols-1 gap-4">
    <UiShortPost v-for="i in data" :item="i" />
  </div>
</template>