<template>
  <main>
    <div
      v-for="item in items"
      :key="item.id"
      class="flex flex-col"
    >
      <div class="flex justify-between mb-2 p-4">
        <div class="flex items-center">
          <img src="https://via.placeholder.com/35?text=user" class="h-8 w-8 rounded-full ring-1 ring-indigo-800 mr-2" alt="user">
          <div class="flex flex-col">
            <small class="font-bold text-xs">{{ item.author }}</small>
            <small class="text-2xs text-gray-500">{{ item.authorTitle }}</small>
          </div>
          <small class="text-2xs font-semibold ml-3">asked {{ item.date }}</small>
        </div>
        <div class="flex items-center">
          <span class="text-sm text-gray-500 mr-2">Category</span>
          <img src="https://via.placeholder.com/25?text=icon" class="rounded-3xl mx-auto" alt="icon">
        </div>
      </div>
      <strong class="text-xl px-4">{{ item.title }}</strong>
      <p class="text-sm px-4">{{ item.content }} <a href="#" class="text-blue-400 hover:text-blue-800">More...</a></p>
      <div class="flex justify-between p-4">
        <div class="flex items-center">
          <div class="flex items-center mr-4">
            <img src="https://via.placeholder.com/25?text=icon" class="rounded-3xl mx-auto" alt="icon">
            <strong class="ml-2 text-sm">{{ item.likes }}</strong>
          </div>
          <div class="flex items-center">
            <img src="https://via.placeholder.com/25?text=icon" class="rounded-3xl mx-auto" alt="icon">
            <span class="ml-2 text-sm">Comment</span>
          </div>
        </div>
        <div class="flex items-center">
          <div class="flex flex-col">
            <small class="font-bold text-xs">{{ item.author }}</small>
            <small class="text-2xs text-gray-500">{{ item.authorTitle }}</small>
          </div>
          <img src="https://via.placeholder.com/35?text=user" class="h-8 w-8 rounded-full ring-1 ring-indigo-800 ml-2" alt="user">
        </div>
      </div>
      <hr v-if="item.id !== items.length" class="my-2">
    </div>
  </main>
</template>
<script>
export default {
  name: "Feed",
  props: {
    items: {
      type: Array,
      required: true,
      default: {}
    }
  }
}
</script>
<style scoped>
</style>
