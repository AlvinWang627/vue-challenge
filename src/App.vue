<script setup>
import RefFamily from './components/easy/2RefFamily.vue'
import LosingReactivity from './components/easy/3LosingReactivity.vue'
import WritableComputed from './components/easy/4WritableComputed.vue'
import WatchFamily from './components/easy/5WatchFamily.vue'
import ShallowRef from './components/easy/6ShallowRef.vue'
import DependencyInjection from './components/easy/9DependencyInjection.vue'
import LifecycleHooks from './components/easy/10LifecycleHooks.vue'
import NextDomUpdate from './components/easy/11NextDomUpdate.vue'
import DynamicCssValues from './components/easy/14DynamicCssValues.vue'
import PreventEventPropagation from './components/easy/243PreventEventPropagation.vue'
import Capitalize from './components/easy/305Capitalize.vue'
import RawApi from './components/medium/7RawApi.vue'
import EffectScopeApi from './components/medium/10EffectScopeApi.vue'
import OptimizePerfDirective from './components/medium/12OptimizePerfDirective.vue'
import UseToggle from './components/medium/15UseToggle.vue'
import Until from './components/medium/16Until.vue'
import UseCounter from './components/medium/17UseCounter.vue'
import UseLocalStorage from './components/medium/18UseLocalStorage.vue'
import VFocus from './components/medium/19VFocus.vue'
import VDebounceClick from './components/medium/20VDebounceClick.vue'
</script>

<template>
  <div class="wrapper">
    <h1>VDebounceClick</h1>
    <VDebounceClick />
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
