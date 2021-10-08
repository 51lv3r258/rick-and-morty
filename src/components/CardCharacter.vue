<template>
  <div class="character">
    <!-- <div class="character_img_container"> -->
    <img :src="character.image" alt="character.name" />
    <!-- </div> -->
    <div class="character_info">
      <h3>
        {{ character.name }}
      </h3>

      <div class="status">
        <span
          :class="
            character.status == 'Alive'
              ? 'alive'
              : character.status == 'Dead'
              ? 'dead'
              : 'default'
          "
        >
        </span>
        <span>{{ character.status }} - {{ character.species }}</span>
      </div>
      <div class="origin">
        <span>
          <span class="origin_title">Origin:</span>
          {{ character.origin.name }}
        </span>
      </div>
      <div class="location">
        <span>
          <span class="origin_title">Location:</span>
          {{ character.location.name }}
        </span>
      </div>
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

<style lang="scss" scoped>
.character {
  background-color: var(--background-card);
  border-radius: 20px;
  transition: transform 500ms cubic-bezier(0.075, 0.82, 0.165, 1);
  overflow: hidden; // * La imagen ahora se adapta con el border radius
  cursor: pointer;
  height: 100%;
  max-width: 18rem;

  &:hover {
    h3 {
      color: var(--text-orange);
    }
    transform: scale(1.05);
  }

  h3 {
    margin-bottom: 0.5rem;
  }

  &_info {
    padding: 1.5rem;

    .status {
      display: flex;
      align-items: center;
      margin-bottom: 0.5rem;
      span {
        color: var(--text-gray);
        &:first-child {
          width: 10px;
          height: 10px;
          border-radius: 100%;
          margin-right: 0.5rem;
        }

        &.alive {
          background-color: green;
        }
        &.dead {
          background-color: red;
        }
        &.default {
          background-color: gray;
        }
      }
    }
    .origin_title {
      font-weight: 600;
    }

    .origin {
      margin-bottom: 0.5rem;
    }
  }

  img {
    max-width: 100%;
    height: auto;
  }
}
</style>