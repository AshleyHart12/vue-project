<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
   <!-- <svg class="background--custom" id="demo" viewBox="0 0 100 100" preserveAspectRatio="none">
      <path fill="#eebc5f" fill-opacity="1" d="M-100 -100L200 -100L200 30L-100 30Z" style="animation: path0 13.048780487804878s linear infinite alternate;" /><path fill="#a1d244" fill-opacity="0.7" d="M-100 -100L200 -100L200 80L-100 80Z" style="animation: path1 19.416666666666666s linear infinite alternate;" /><path fill="#b0b43d" fill-opacity="0.1" d="M-100 -100L200 -100L200 70L-100 70Z" style="animation: path2 19.102040816326531s linear infinite alternate;" />
    </svg> -->
  <header>
    <div class="wrapper">
      <HelloWorld msg="Welcome" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/movies">Movies</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}

path {
        transform-origin: 50% 0%;
      }
      .background--custom {
        background-color: #FFFFFF;
        position: absolute;
        width: 100vw;
        height: 100vh;
        z-index: -1;
        top: 0;
        left: 0;
      }
      @keyframes path0 {
        0% {
          transform: rotate(-50deg);
        }
        100% {
          transform: rotate(50deg);
        }
      }
      @keyframes path1 {
        0% {
          transform: rotate(-10deg);
        }
        100% {
          transform: rotate(10deg);
        }
      }
      @keyframes path2 {
        0% {
          transform: rotate(0deg);
        }
        100% {
          transform: rotate(0deg);
        }
      }
</style>
