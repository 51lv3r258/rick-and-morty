<template>
  <div class="character">
    <div class="character_info">
      {{ character.name }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    character: {
      type: Object,
      default: null,
    },
  },
};
</script>

<style>
</style>