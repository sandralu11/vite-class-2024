<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink> | <RouterLink to="/w1">W1:Todos</RouterLink> |
        <RouterLink to="/w2">W2:composition</RouterLink> |
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped></style>
