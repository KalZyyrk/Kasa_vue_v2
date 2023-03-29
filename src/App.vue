<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <header>
    <RouterLink to="/">
      <img alt="kasa logo" class="logo" src="@/assets/logo.svg" height="68" />
    </RouterLink>
      <nav>
        <RouterLink to="/">Accueil</RouterLink>
        <RouterLink to="/about">A Propos</RouterLink>
      </nav>

  </header>
  <RouterView />
  <footer>
    <img alt="kasa logo" class="logo" src="@/assets/logo-white.svg" width="122"/>
    <p>© 2020 Kasa. All rights reserved</p>
  </footer>
</template>

<style scoped>
  header {
    margin-top: 40px;
    display: flex;
    justify-content: space-between;
  }
  nav {
    display: flex;
    justify-content: space-between;
    width: 309px;
    align-items: center;
    text-align: right;
  }

  nav a{
    font-size: 24px;
    text-decoration: none;
    color: var(--orange);
    font-weight: 500;
  }

  nav a:hover, .active-link {
    text-decoration: underline;
  }

  footer {
    background-color: #000000;
    padding-top: 4rem;
    height: 209px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2.5rem;
  }

  footer p {
    font-size: 24px;
    font-weight: 500;
    color: var(--white);
    text-align: center; 
  }

  @media screen and (max-width: 580px) {
    header .logo{
      height: 45px;
    }

    nav {
      width: 140px;
    }

    nav a {
      font-size: 12px;
    }

    footer p {
      font-size: 12px;
    }
  }

</style>
