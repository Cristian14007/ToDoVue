<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import NewTask from './components/NewTask.vue'
import List from './components/List.vue'
import CounterTask from './components/CounterTask.vue'

import { reactive } from 'vue'

const todos = reactive([
  {
    id:0,
    name: 'Task 1',
    completed: false
  },
  {
    id:1,
    name: 'Task 2',
    completed: true
  },
  {
    id:2,
    name: 'Task 3',
    completed: true
  },
  {
    id:3,
    name: 'Task 4',
    completed: false
  }
])

const classObject = reactive({
  completed: true,
  'text-decoration': "underline"
})

</script>

<template>
  <header>
    <!-- <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" /> -->

    <Header></Header>
  </header>
  
  
  
  

 <main>
  <NewTask></NewTask>
  <List :todos="todos"></List>
  <CounterTask></CounterTask>
    
 </main>
  

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
</style>
