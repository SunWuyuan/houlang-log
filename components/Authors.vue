<template>
  <div class="flex -space-x-2 relative z-0 overflow-hidden mt-6">
    <img v-for="(author, i) in authors" 
    :key="i" 
    class="relative inline-block h-8 w-8 rounded-full ring-2 ring-white"
    :style="{ zIndex: authors.length - i }" 
    :src="authorList[author]" 
    alt="" />
  </div>
</template>

<script setup>
const props = defineProps({
  authors: String,
  authorList: {
    type: Object,
    default: () => ({
      "houlang": "https://www.langs.ink/logo-jpg.jpg",
      "wuyuan": "https://www.langs.ink/sunwuyuan-logo.webp", 
      "guaning": "https://www.langs.ink/guaning-logo.webp",
      "shiqian": "https://www.langs.ink/shiqian-logo.webp"
    }),
  },
});
var authorsStr = String(props.authors);
const authors = authorsStr.split(',');
</script>
