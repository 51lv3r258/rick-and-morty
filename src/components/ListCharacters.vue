<template>
  <section>
    <div class="characters">
      <div
        class="characters_item"
        v-for="character in characters"
        :key="character.id"
      >
        <CardCharacter :character="character" />
      </div>
    </div>
  </section>
</template>

<script>
import { computed, onMounted } from "vue";
import { useStore } from "vuex";

import CardCharacter from "@/components/CardCharacter";

export default {
  components: {
    CardCharacter,
  },
  setup() {
    const store = useStore();

    const characters = computed(() => store.state.charactersFilter);

    onMounted(() => {
      store.dispatch("getCharacters");
    });

    return {
      characters,
    };
  },
};
</script>

<style lang="scss" scoped >
.characters {
  display: grid;
  grid-auto-flow: dense;
  // grid-template-columns: repeat(auto-fill, minmax(15rem, 1fr));
  grid-template-columns: repeat(auto-fill, minmax(min(100%, 15rem), 1fr));
  column-gap: 1rem;
  row-gap: 1.5rem;

  &_item {
    display: grid;
    justify-content: center;
  }
}
</style>