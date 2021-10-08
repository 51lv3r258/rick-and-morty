<template>
  <div class="container">
    <div class="sub_container">
      <h1>Rick and Morty</h1>
      <ListCharacters />
    </div>
  </div>
</template>

<script>
import ListCharacters from "@/components/ListCharacters";

export default {
  name: "App",
  components: {
    ListCharacters,
  },
};
</script>

<style lang="scss">
:root {
  --background-body: #24282f;
  --background-card: #3c3e44;
  --text-white: #ffffff;
  --text-gray: #c0c0c0;
  --text-orange: #ff9800;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  background-color: var(--background-body);
  color: var(--text-white);
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

h1 {
  margin-bottom: 3rem;
  text-align: center;
}

.container {
  display: grid;
  place-items: center;
  width: 100%;
  height: auto;

  .sub_container {
    width: 100%;
    margin-top: 5rem;
    max-width: 986px;
    padding: 0 32px;
  }
}
</style>
