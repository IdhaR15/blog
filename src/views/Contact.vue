<template>
  <div class="container">
    <div class="row">
      <div class="col-md-6 contact">
        <h1>contact</h1>

        <FormContact />
      </div>
    </div>
  </div>
</template>

<script>
import FormContact from "../components/FormContact.vue";
export default {
  components: {
    FormContact,
  },
};
</script>

<style scoped>
.contact {
  text-align: left;
}
</style>
