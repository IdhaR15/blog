<template>
  <div>
    <div class="alert alert-success" v-if="pesan">pesan terkirim!</div>
    <form @submit.prevent="kirimPesan">
      <div class="form-group">
        <label for="">NAMA</label>
        <input type="text" v-model="contact.nama" class="form-control" />
      </div>
      <div class="form-group">
        <label for="">EMAIL</label>
        <input type="email" v-model="contact.email" class="form-control" />
      </div>
      <div class="form-group">
        <label for="">SUBJEK</label>
        <input type="text" v-model="contact.subjek" class="form-control" />
      </div>
      <div class="form-group">
        <label for="">PESAN</label>
        <textarea v-model="contact.pesan" cols="30" rows="5" class="form-control"></textarea>
      </div>
      <button class="btn btn-danger">Kirim</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      contact: {
        nama: "",
        email: "",
        subjek: "",
        pesan: "",
      },
      pesan: false,
    };
  },

  methods: {
    async kirimPesan() {
      const { data, error } = await this.$supabase.from("tb_kontak").insert([this.contact]);

      if (data) this.pesan = true;
    },
  },
};
</script>

<style lang="scss" scoped></style>
