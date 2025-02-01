<template>
  <div class="container d-flex justify-content-center align-items-center min-vh-100">
    <div class="card shadow" style="width: 400px;">
      <div class="card-body">
        <h2 class="card-title text-center">Login</h2>
        <form @submit.prevent="handleLogin">
          <div class="mb-3">
            <label for="email" class="form-label">Email</label>
            <input
              type="email"
              class="form-control"
              id="email"
              v-model="email"
              placeholder="Enter email"
              required
            />
          </div>
          <div class="mb-3">
            <label for="password" class="form-label">Password</label>
            <input
              type="password"
              class="form-control"
              id="password"
              v-model="password"
              placeholder="Enter password"
              required
            />

          </div>
          <button type="submit" class="btn btn-primary w-100">Login</button>
        </form>
        <p v-if="errorMessage" class="text-danger text-center mt-3">{{ errorMessage }}</p>
      </div>
    </div>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      password: '',
      errorMessage: '',
    };
  },
  methods: {
    handleLogin() {
      // Simulasi login
      if (this.email === 'user@example.com' && this.password === '123') {
        // Simulasikan penyimpanan data login (misal menggunakan localStorage)
        localStorage.setItem('isAuthenticated', true);
        this.$router.push ('/dasbor')
      } else {
        this.errorMessage = 'Email atau password salah!';
      }
    },
  },
};
</script>

<style scoped>
.card {
  max-width: 100%;
  border-radius: 10px;
}

button {
  font-size: 16px;
}

.error {
  font-size: 14px;
  color: red;
}
</style>
