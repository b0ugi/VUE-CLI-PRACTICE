<template>
  <li>
    <h2>{{ name }} {{ favFriend ? "(Favourite)" : "" }}</h2>
    <button @click="toggleFavourite">Favourite</button>
    <button @click="toggleVisibility">
      {{ detailVisibility ? "Hide" : "Show" }} Details
    </button>
    <ul v-show="detailVisibility">
      <li><strong>Phone: </strong> {{ phoneNumber }}</li>
      <li><strong>Email: </strong> {{ emailAddress }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      isRequired: true,
    },
    phoneNumber: {
      type: String,
      isRequired: true,
    },
    emailAddress: {
      type: String,
      isRequired: true,
    },
    isFavourite: {
      type: Boolean,
      isRequired: false,
    },
  },

  data() {
    return {
      detailVisibility: false,
      favFriend: this.isFavourite,
    };
  },

  methods: {
    toggleVisibility() {
      this.detailVisibility = !this.detailVisibility;
    },

    toggleFavourite() {
      this.favFriend = !this.favFriend;
    },
  },
};
</script>

<style>
</style>