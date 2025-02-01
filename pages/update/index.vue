<template>
  <div class="container">
    <h2 class="text-center my-4">Update Berita</h2>
    <form @submit.prevent="submitNews">
      <div class="mb-3">
        <label for="title" class="form-label">Judul Berita</label>
        <input
          type="text"
          id="title"
          class="form-control"
          v-model="title"
          required
        />
      </div>
      <div class="mb-3">
        <label for="content" class="form-label">Isi Berita</label>
        <textarea
          id="content"
          class="form-control"
          v-model="content"
          rows="5"
          required
        ></textarea>
      </div>
      <button type="submit" class="btn btn-primary w-100">Submit Berita</button>
    </form>

    <div v-if="newsSubmitted" class="alert alert-success mt-4">
      Berita berhasil diperbarui!
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: '',
      content: '',
      newsSubmitted: false,
    };
  },
  methods: {
    submitNews() {
      // Simulasi penyimpanan berita, bisa diganti dengan API call
      console.log('Berita yang diupdate:', {
        title: this.title,
        content: this.content,
      });

      // Tampilkan konfirmasi
      this.newsSubmitted = true;

      // Reset form
      this.title = '';
      this.content = '';
    },
  },
};
</script>
