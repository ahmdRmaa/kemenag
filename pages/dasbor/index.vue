<template>
  <div class="container">
    <h1 class="text-center my-4">Dashboard</h1>
    <p class="text-center">Selamat datang, Anda sudah login!</p>

    <div class="text-center">
      <router-link to="/update" class="btn btn-success">Update Berita</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Dashboard',
  created() {
    if (!localStorage.getItem('isAuthenticated')) {
      this.$router.push('/'); // Redirect ke halaman login jika belum login
    }
  },
};
</script>
