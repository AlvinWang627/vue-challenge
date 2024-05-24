<script setup>
import RefFamily from './components/2RefFamily.vue'
import LosingReactivity from './components/3LosingReactivity.vue'
import WritableComputed from './components/4WritableComputed.vue'
import WatchFamily from './components/5WatchFamily.vue'
import ShallowRef from './components/6ShallowRef.vue'
</script>

<template>
  <div class="wrapper">
    <!-- <div>
      <h1>2 RefFamily</h1>
      <RefFamily />
    </div>
    <div>
      <h1>3 LosingReactivity</h1>
      <LosingReactivity />
    </div> -->
    <!-- <div>
      <h1>4 WritableComputed</h1>
      <WritableComputed />
    </div> -->
    <!-- <div>
      <h1>5 WatchFamily</h1>
      <WatchFamily />
    </div> -->
        <div>
      <h1>6 ShallowRef</h1>
      <ShallowRef />
    </div>
  </div>
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
</style>
