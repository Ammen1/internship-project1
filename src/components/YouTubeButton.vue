<template>
  <a
    :href="href"
    target="_blank"
    class="px-3 py-2 rounded border-2 text-white border-orange-600 bg-red-500 hover:bg-blue-600 transition-colors"
  >
    <slot>YouTube</slot>
    
  </a>

<div id="app">
  <heart-btn>Like</heart-btn>
</div>
   
</template>

<script setup>
const props = defineProps({
  href: String
})

</script>
