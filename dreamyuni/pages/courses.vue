<template>
  <div class="dashboard-container">
    <!-- Header -->
    <header class="dashboard-header">
      <div class="logo">
        <img src="https://placehold.co/200x100?text=Dreamy+Uni" alt="Dreamy Uni Logo" />
      </div>
      <div class="search-bar">
        <input type="text" placeholder="Search..." />
        <button><i class="fas fa-search"></i></button>
      </div>
      <div class="user-profile">
        <img src="https://placehold.co/200x100?text=Dreamy+Uni" alt="User Avatar" class="avatar" />
        <span class="username">John Doe</span>
        <div class="dropdown">
          <button class="dropbtn"><i class="fas fa-caret-down"></i></button>
          <div class="dropdown-content">
            <a href="#">Profile</a>
            <a href="#">Settings</a>
            <a href="#">Logout</a>
          </div>
        </div>
      </div>
      <div class="notifications">
        <i class="fas fa-bell"></i>
        <span class="notification-count">3</span>
      </div>
    </header>

    <!-- Main Content Area -->
    <main class="dashboard-content">
      <h1 class="dashboard-title">Course Dashboard</h1>

      <!-- Error Message -->
      <div class="error-message">
        <h2>404 - Page Not Found</h2>
        <p>Sorry, the page you are looking for does not exist or has been moved.</p>
        <a href="/" class="btn-primary">Go to Homepage</a>
      </div>
    </main>

    <!-- Footer -->
    <footer class="dashboard-footer">
      <p>&copy; 2023 Dreamy Uni. All rights reserved.</p>
      <nav>
        <a href="#">Terms of Service</a>
        <a href="#">Privacy Policy</a>
        <a href="#">Contact Us</a>
      </nav>
    </footer>
  </div>
</template>

<script setup lang="ts">
import { onMounted, ref } from 'vue';

definePageMeta({
  layout: "navbar",
});

onMounted(() => {
  console.error('404 - Page Not Found');
});
</script>

<style scoped>
.dashboard-container {
  display: grid;
  grid-template-areas:
    "header"
    "main"
    "footer";
  grid-template-columns: 1fr;
  grid-template-rows: auto 1fr auto;
  height: 100vh;
}

.dashboard-header {
  grid-area: header;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
  background-color: #ffffff;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.dashboard-content {
  grid-area: main;
  padding: 2rem;
  overflow-y: auto;
  display: flex;
  justify-content: center;
  align-items: center;
}

.dashboard-footer {
  grid-area: footer;
  background-color: #f8f9fa;
  padding: 1rem;
  text-align: center;
}

.error-message {
  text-align: center;
  max-width: 600px;
}

.error-message h2 {
  font-size: 2.5rem;
  color: #dc3545;
  margin-bottom: 1rem;
}

.error-message p {
  font-size: 1.2rem;
  color: #6c757d;
  margin-bottom: 2rem;
}

.btn-primary {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  background-color: #007bff;
  color: white;
  text-decoration: none;
  border-radius: 4px;
  font-weight: bold;
  transition: background-color 0.3s ease;
}

.btn-primary:hover {
  background-color: #0056b3;
}

/* Existing styles... */
</style>
