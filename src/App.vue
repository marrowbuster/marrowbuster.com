<script setup>
  import { RouterView } from 'vue-router'
  import Logo from './components/icons/Logo.vue';
  import CoolHeader from './components/CoolHeader.vue';
  import NavigationBar from './components/NavigationBar.vue';
</script>

<template>
  <aside>
    <Logo id="logo"></Logo>
    <NavigationBar></NavigationBar>
  </aside>

  <div>
    <header>
      <CoolHeader></CoolHeader>
    </header>

    <main class="page-filter">
      <div class="page-shape" id="main-page">
        <RouterView />
      </div>
    </main>
  </div>
</template>

<style>
  main {
    flex: 1;
  }

  /*
   * Trimmed page borders with modifiable parameters.
   * Each corner trimmed corner starts and ends at horizontal or vertical offsets by var(--trim-size).
   * The linear-gradient simulates a border at the trims' half-diagonals, computed as (sqrt(2) * a) / 2.
   * The -1px are for formula corrections.
   * "background-color" must come after "background".
   */
  .page-shape {
    --border-width: 1px;
    --trim-size: 50px;
    --border-color: black;

    border: var(--border-width) solid var(--border-color);

    clip-path: polygon(var(--trim-size) 0, 100% 0, 100% calc(100% - var(--trim-size)), calc(100% - var(--trim-size)) 100%, 0 100%, 0 var(--trim-size));
    background: linear-gradient(135deg, var(--border-color) calc(0.707106 * var(--trim-size) + var(--border-width)), #0000 0, var(--border-color) calc(100% - 0.707106 * var(--trim-size) + var(--border-width))) border-box;
    background: linear-gradient(135deg,
        #000000FF calc(0.707 * var(--trim-size) + var(--border-width) - 1px),
        #FFFFFF00 calc(0.707 * var(--trim-size) + var(--border-width) - 1px),
        #FFFFFF00 calc(100% - 0.707 * var(--trim-size) + var(--border-width) - 1px),
        #000000FF calc(100% - 0.707 * var(--trim-size) + var(--border-width)));
    background-color: #FDFDFD;
  }

  .page-filter {
    filter: drop-shadow(-3px 3px 2px rgba(105, 105, 105, 0.5));
  }

  #main-page {
    padding: 1.5rem 2.5rem;
    height: 100%;
  }

  #logo {
    max-height: 211px;
    max-width: 211px;
  }

  @media screen and (max-width: 992px) {
    aside {
      flex-direction: row !important;
    }

    main,
    aside {
      font-size: 0.8em;
    }

    #logo {
      max-height: 160px;
      max-width: 160px;
    }
  }
</style>