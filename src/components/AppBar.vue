<template>
  <nav>
    <div class="appbar">
      <router-link class="logo" :to="{ name: 'Home' }">
        <img src="../assets/vue.png" id="vue">
        <span>Vue</span>
      </router-link>
      <div class="menu">
        <router-link v-for="link in nav" :to="{ name: link }">
          {{ link }}
        </router-link>
      </div>
      <div class="toggle center" onclick="this.classList.toggle('active');document.querySelector('.menu').classList.toggle('active')">
        <svg class="ham hamRotate ham4" viewBox="0 0 100 100" width="50">
          <path
                class="line top"
                d="m 70,33 h -40 c 0,0 -8.5,-0.149796 -8.5,8.5 0,8.649796 8.5,8.5 8.5,8.5 h 20 v -20" />
          <path
                class="line middle"
                d="m 70,50 h -40" />
          <path
                class="line bottom"
                d="m 30,67 h 40 c 0,0 8.5,0.149796 8.5,-8.5 0,-8.649796 -8.5,-8.5 -8.5,-8.5 h -20 v 20" />
        </svg>
      </div>
    </div>
  </nav>
</template>

<script>
  export default {
    mounted() {
      window.requestAnimationFrame(this.update)
    },
    methods: {
      update() {
        const r = this.$route
        if (r.name) {
          document.title = this.$route.name
        } else {
          document.title = 'Vue + Vite + Esfract'
        }
        window.requestAnimationFrame(this.update)
      }
    },
    data() {
      return {
        nav: [
          'About',
          'Esfract',
        ]
      }
    }
  }
</script>

<style scoped>
  nav {
    width: calc(100vw - 10px);
    display: flex;
    align-items: center;
    height: 60px;
    box-sizing: border-box;
    border-bottom: solid 2px #eee;
    position: fixed;
    background: white;
    z-index: 100;
    top: 0;
  }

  .appbar {
    position: relative;
    display: flex;
    align-items: center;
    height: 100%;
    width: 1200px;
    margin: 0 auto;
    box-sizing: border-box;
    padding: 0 20px;
    justify-content: space-between;
  }
  
  #vue {
    width: 36px;
    margin: 0 10px 0 0;
  }

  .logo {
    display: flex;
    align-items: center;
    height: 100%;
    color: var(--dark);
    transition: 0.2s;
  }

  .logo:hover {
    color: var(--dark);
    opacity: 0.75;
  }

  .menu {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    height: 100%;
    transition: 0.5s;
  }

  .menu a {
    display: flex;
    align-items: center;
    padding: 0 10px;
    height: 100%;
  }

  .toggle {
    display: none;
    position: absolute;
    right: 0;
    top: 0;
    width: 60px;
    height: 60px;
    background: transparent;
  }

  .ham {
    cursor: pointer;
    -webkit-tap-highlight-color: transparent;
    transition: transform 400ms;
    -moz-user-select: none;
    -webkit-user-select: none;
    -ms-user-select: none;
    user-select: none;
  }
  .active .hamRotate {
    transform: rotate(45deg);
  }
  .active .hamRotate180 {
    transform: rotate(180deg);
  }
  .line {
    fill: none;
    transition: stroke-dasharray 400ms, stroke-dashoffset 400ms;
    stroke: var(--dark);
    stroke-width: 5.5;
    stroke-linecap: round;
  }
  .ham4 .top {
    stroke-dasharray: 40 121;
  }
  .ham4 .bottom {
    stroke-dasharray: 40 121;
  }
  .active .ham4 .top {
    stroke-dashoffset: -68px;
  }
  .active .ham4 .bottom {
    stroke-dashoffset: -68px;
  }

  @media screen and (max-width: 800px) {
    .toggle {
      display: flex;
    }

    .menu {
      opacity: 0;
      position: fixed;
      left: 100vw;
      top: 60px;
      width: calc(100vw - 10px);
      height: calc(100vh - 60px);
      flex-direction: column;
      justify-content: flex-start;
      background: #ffffff80;
      backdrop-filter: blur(4px);
    }

    .menu.active {
      opacity: 1;
      left: 0;
      top: 60px;
    }

    .menu a {
      width: 100%;
      padding: 0;
      justify-content: center;
      height: 60px;
    }
  }
</style>