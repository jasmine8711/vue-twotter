<template>
  <div
    class="twoot-item bg-white m-3 p-3 rounded shadow"
    @click="favouriteTwoot(twoot.id)"
  >
    <div class="user-profile_twoot">
      <div class="text-primary">@{{ username }}</div>
      <div class="twoot-item_content">
        {{ twoot.content }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TwootItem",
  props: {
    username: {
      type: String,
      required: true,
    },
    twoot: {
      type: Object,
      required: true,
    },
  },
  methods: {
    favouriteTwoot(id) {
      this.$emit("favourite", id);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.twoot-item {
  cursor: pointer;
  transition: all 0.25s ease;
}
.twoot-item:hover {
  transform: scale(1.1, 1.1);
}

.twoot-item__user {
  font-weight: bold;
}
</style>
