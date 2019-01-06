<template>
  <div id="app">
    <app-header/>

    <ul class="desktop">
      <li class="desktop__app icon" v-for="item in 30" :key="item">
        <img
          class="desktop__image"
          src="./assets/images/icons/music.svg"
          alt="img"
        >
        <span class="desktop__text">Music - {{item}}</span>
      </li>
    </ul>

    <router-view/>

    <app-footer/>
  </div>
</template>

<script>
    import AppHeader from '@/components/AppHeader';
    import AppFooter from '@/components/AppFooter';

    export default {
        components: {
            AppHeader,
            AppFooter,
        }
    };
</script>

<style lang="scss">
  * {
    box-sizing: border-box;
  }

  body {
    background-color: #000;
    background-image: url('./assets/images/bg.jpeg');
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    background-attachment: fixed;
    font-family: 'Helvetica', sans-serif;
    margin: 0;
    padding: 0;
    overflow: hidden;
    perspective-origin: 0 0;
  }

  .desktop {
    list-style-type: none;
    padding: 20px;
    margin-top: 0;
    margin-bottom: 0;
    height: calc(100vh - 90px);
    overflow-y: auto;

    display: grid;
    grid-template-columns: repeat(7, 1fr);
    grid-gap: 25px;
    grid-auto-rows: minmax(120px, 120px);
    grid-auto-flow: revert;

    .desktop__app {
      display: block;
      z-index: 1;
      text-align: center;
      box-shadow: 0 0 10px rgba(255, 255, 255, 0.75);
      padding: 10px;
      border-radius: 10px;
      background-color: rgba(255, 255, 255, 0.1);
    }

    .desktop__image {
      display: block;
      margin-left: auto;
      margin-right: auto;
      width: 75px;
      border: 2px solid rgba(225, 225, 225, 0.0);
      border-radius: 6px;
      transition: all 0.2s;
    }

    .desktop__text {
      color: #ffffff;
    }
  }
</style>
