<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h2>{{ nama }}</h2>

    <button class="btn btn-info" @click="tambahSatu">{{ counter }}</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nama: "zul hilmi",
      counter: 0,
    };
  },

  methods: {
    tambahSatu() {
      this.counter = this.counter + 1;
    },
  },
};
</script>
