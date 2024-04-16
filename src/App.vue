<script setup>
  import { RouterLink, RouterView } from 'vue-router'
  import Logo from './components/icons/Logo.vue';
  import CustomList from './components/CustomList.vue';
</script>

<template>
  <header>
    <h1 id="title">marrowbuster</h1>
  </header>

  <aside>
    <Logo width="200px"></Logo>
    <nav>
      <CustomList id="nav-links">
        <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 -960 960 960" width="24">
          <path
            d="M240-200h120v-240h240v240h120v-360L480-740 240-560v360Zm-80 80v-480l320-240 320 240v480H520v-240h-80v240H160Zm320-350Z" />
        </svg>
        <RouterLink to="/">home</RouterLink>
        <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 -960 960 960" width="24">
          <path
            d="M320-240h320v-80H320v80Zm0-160h320v-80H320v80ZM240-80q-33 0-56.5-23.5T160-160v-640q0-33 23.5-56.5T240-880h320l240 240v480q0 33-23.5 56.5T720-80H240Zm280-520v-200H240v640h480v-440H520ZM240-800v200-200 640-640Z" />
        </svg>
        <RouterLink to="/about">about</RouterLink>
        <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 -960 960 960" width="24">
          <path
            d="M160-160q-33 0-56.5-23.5T80-240v-480q0-33 23.5-56.5T160-800h640q33 0 56.5 23.5T880-720v480q0 33-23.5 56.5T800-160H160Zm0-80h640v-400H160v400Zm140-40-56-56 103-104-104-104 57-56 160 160-160 160Zm180 0v-80h240v80H480Z" />
        </svg>
        <RouterLink to="/projects">projects</RouterLink>
        <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 -960 960 960" width="24">
          <path
            d="M160-160q-33 0-56.5-23.5T80-240v-480q0-33 23.5-56.5T160-800h640q33 0 56.5 23.5T880-720v480q0 33-23.5 56.5T800-160H160Zm320-280L160-640v400h640v-400L480-440Zm0-80 320-200H160l320 200ZM160-640v-80 480-400Z" />
        </svg>
        <RouterLink to="/contact">contact</RouterLink>
        <span>$</span>
        <RouterLink to="/commissions">commission info</RouterLink>
        <span>!</span>
        <RouterLink to="/tos">terms of service</RouterLink>
      </CustomList>
    </nav>
  </aside>

  <main>
    <RouterView />
  </main>
</template>

<style>
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
    /* Original:
      text-shadow: 0 1px 0 #ccc, 0 2px 0 #ccc,
      0 3px 0 #ccc, 0 4px 0 #ccc,
      0 5px 0 #ccc, 0 6px 0 #ccc,
      0 7px 0 #ccc, 0 8px 0 #ccc,
      0 9px 0 #ccc, 0 10px 0 #ccc,
      0 11px 0 #ccc, 0 12px 0 #ccc,
      0 10px 30px rgba(0, 0, 0, 0.5);
      */
    font-size: 4rem;
    margin: 0;
    letter-spacing: 0.1em;
    color: #EEE;
    -webkit-text-stroke: 0.1px #222;
  }

  #app {
    display: grid;
    grid-template-columns: 0.5fr 1.5fr;
    grid-template-rows: 0.2fr 1.5fr;
    gap: 20px 20px;
    grid-template-areas:
      "aside header"
      "aside main";
    width: 100%;
    max-width: 1000px;
    height: 100%;
  }

  main {
    grid-area: main;
    background: #FDFDFD;
    padding: 1.5rem 2.5rem;
    border: 1px solid;
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

  nav {
    background: #FDFDFD;
    padding: 1.1em;
    width: 100%;
    min-height: 500px;
    border: 1px solid;
  }

  #nav-links > span {
    font-weight: bold;
  }

  @media (max-width: 992px) {
    #app {
      display: flex;
      flex-direction: column;
    }
  }
</style>
