<script setup>
  import { RouterView } from 'vue-router'
  import Logo from './components/icons/Logo.vue';
  import CoolHeader from './components/CoolHeader.vue';
  import NavigationBar from './components/NavigationBar.vue';
</script>

<template>
  <CoolHeader></CoolHeader>

  <aside>
    <Logo width="100%"></Logo>
    <NavigationBar></NavigationBar>
  </aside>

  <main class="page-filter">
    <div class="page-shape" id="main-page">
      <RouterView />
    </div>
  </main>
</template>

<style>
  main {
    grid-area: main;
  }

  aside {
    grid-area: aside;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
  }

  header {
    grid-area: header;
  }

  /*
   * Trimmed paper borders.
   */
  .page-shape {
    --border-width: 1px;
    --trim-size: 50px;
    --border-color: black;

    border: var(--border-width) solid var(--border-color);

    clip-path: polygon(var(--trim-size) 0, 100% 0, 100% 100%, 0 100%, 0 var(--trim-size));
    background: linear-gradient(135deg, var(--border-color) calc(0.707 * var(--trim-size) + var(--border-width)), #0000 0) border-box;
    /* MUST come after! */
    background-color: #FDFDFD;
    border-bottom-right-radius: 30px;
  }

  .page-filter {
    filter: drop-shadow(-3px 3px 2px rgba(105, 105, 105, 0.5));
  }

  #main-page {
    padding: 1.5rem 2.5rem;
    height: 100%;
  }

  @media (max-width: 992px) {
    header {
      text-align: center;
    }

    #title {
      font-size: 10vw;
    }

    aside {
      flex-direction: row;
    }
  }
</style>