<script setup>
import { useRoute } from 'vue-router';

const route = useRoute();
</script>

<template>
  <nav class="navbar fixed-top navbar-expand-lg bg-light navbar-light">
    <div class="container-fluid">
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
        data-bs-target="#navbarNav" aria-controls="navbarNav"
        aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">

          <li class="nav-item px-3" >
            <router-link class="nav-link text-dark" :to="{ name: 'Home' }">
              Home
            </router-link>
          </li>
          <li class="nav-item px-3" v-if="route.name !== 'MyCV'">
            <a class="nav-link text-dark" href="#projects">Web Application Projects</a>
          </li>

          <li class="nav-item px-3" v-if="route.name !== 'MyCV'">
            <a class="nav-link text-dark" href="#contact">Contact</a>
          </li>

        </ul>
      </div>
    </div>
  </nav>
</template>
