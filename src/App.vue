<script setup>
  import { RouterLink, RouterView } from 'vue-router'
  import Logo from './components/icons/Logo.vue';
  import NavigationBar from './components/NavigationBar.vue';
</script>

<template>
  <header>
    <h1 id="title">marrowbuster</h1>
  </header>

  <aside>
    <Logo width="100%"></Logo>
    <NavigationBar></NavigationBar>
  </aside>

  <main>
    <RouterView />
  </main>
</template>

<style scoped>
  @font-face {
    font-family: 'Twitcher';
    src: url(@/assets/fonts/twitcher.woff2) format('woff2');
    font-display: swap;
  }

  #title {
    text-shadow: 0 1px 0 #999, 0 2px 0 #999,
      -1px 3px 0 #888, -1px 4px 0 #888,
      -2px 5px 0 #777, -2px 6px 0 #777,
      -3px 7px 0 #666, -3px 8px 0 #666,
      -3px 9px 0 #555, -3px 10px 0 #555,
      -4px 11px 0 #444, -4px 12px 0 #444,
      -4px 10px 30px rgba(0, 0, 0, 0.5);
    font-size: 84px;
    margin: 0;
    letter-spacing: 0.1em;
    color: #EEE;
    -webkit-text-stroke: 0.1px #222;
  }

  main {
    grid-area: main;
    padding: 1.5rem 2.5rem;
  }

  /*
   * Trimmed paper borders.
   */
  main,
  nav {
    border: var(--border-width) solid var(--border-color);

    --border-width: 1px;
    --trim-size: 50px;
    --border-color: black;

    clip-path: polygon(var(--trim-size) 0, 100% 0, 100% 100%, 0 100%, 0 var(--trim-size));
    background: linear-gradient(135deg, var(--border-color) calc(0.707 * var(--trim-size) + var(--border-width)), #0000 0) border-box;
    /* MUST be after! */
    background-color: #FDFDFD;
  }

  /*
   * Trim override.
   */
  nav {
    --trim-size: 25px;

    /* 
     * Trim top-left and bottom-right if needed.
     *
    clip-path: polygon(var(--trim-size) 0,
        100% 0,
        100% calc(100% - var(--trim-size)),
        calc(100% - var(--trim-size)) 100%,
        0 100%,
        0 var(--trim-size));
     */
    border-bottom-right-radius: 30px;
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