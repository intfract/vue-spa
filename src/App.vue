<template>
  <AppBar></AppBar>
  <router-view></router-view>
</template>

<script>
  import AppBar from './components/AppBar.vue'
  export default {
    components: {
      'AppBar': AppBar,
    },
    data() {
      return {
        
      }
    },
    mounted() {
      
    },
    methods: {
      
    }
  }
</script>

<style>
  :root {
    --accent: #357BF2;
    --blue: #357BF2;
    --red: #E1503C;
    --yellow: #EEA71F;
    --green: #0CC98D;
    --dark: #36393F;
    --darker: #2F3136;
    --darkest: #202225;
  }

  body {
    font-family: 'Lexend Deca';
    width: 100vw;
    margin: 0;
    padding: 0;
    height: 100vh;
    font-size: 16px;
    color: var(--dark);
  }

  ::-webkit-scrollbar {
    width: 10px;
  }
  
  ::-webkit-scrollbar-track {
    background: white;
  }
  
  ::-webkit-scrollbar-thumb {
    background: var(--dark);
    border-radius: 5px;
  }
  
  ::-webkit-scrollbar-thumb:hover {
    background: var(--darker);
  }

  #app {
    width: 100vw;
    height: 100vh;
    margin: 0;
    padding: 0;
    overflow-x: hidden;
    overflow-y: scroll;
    flex-direction: column;
  }

  h1, h2, h3 {
    margin: 0;
    font-weight: 400;
    transition: 0.25s;
    text-transform: capitalize;
  }

  h1 {
    color: var(--darkest);
    font-size: 48px;
  }

  h2 {
    margin: 10px 0;
    color: var(--darker);
    font-size: 36px;
  }
  
  h3 {
    color: var(--dark);
    font-size: 24px;
  }

  p {
    margin: 0;
  }

  a, button, input {
    outline: none;
  }

  a {
    color: var(--dark);
    text-decoration: none;
    transition: 0.2s;
  }

  p a {
    color: var(--accent);
  }

  a:hover {
    color: var(--accent);
  }

  p a:hover {
    opacity: 0.75;
  }

  button {
    font-weight: 400;
    display: flex;
    flex-direction: row;
    padding: 10px 20px;
    font-size: 16px;
    background: var(--accent);
    border: none;
    outline: none;
    font-family: 'Lexend Deca';
    border-radius: 6px;
    color: white;
    transition: 0.2s;
    user-select: none;
  }

  button:hover {
    transform: scale(0.95);
  }

  .center {
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>