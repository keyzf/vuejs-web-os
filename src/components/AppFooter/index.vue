<template>
  <footer class="app-footer">
    <ul class="app-footer__list">
      <li class="app-footer__item">
        <img
          src="../../assets/images/icons/finder.png"
          alt="img"
        >
      </li>
      <li class="app-footer__item closed">
        <img
          src="../../assets/images/icons/music.svg"
          alt="img"
        >
      </li>
      <li class="app-footer__item closed">
        <img
          src="../../assets/images/icons/calc.png"
          alt="img"
        >
      </li>
      <li class="app-footer__item">
        <img
          src="../../assets/images/icons/settings.png"
          alt="img"
        >
      </li>
    </ul>
  </footer>
</template>

<script>
    export default {
        name: "AppFooter",
    };
</script>

<style lang="scss" scoped>
  .app-footer {
    display: inline-block;
    padding: 5px 20px;
    text-align: center;
    position: absolute;
    left: 50%;
    bottom: 0;
    transform: translateX(-50%);
    border-radius: 10px;
    background-color: rgba(39, 39, 39, .9);

    .app-footer__list {
      display: inline-block;
      margin: 0 5px;
      padding: 0;
      transform-origin: bottom center;
    }

    .app-footer__item {
      display: inline-block;
      vertical-align: top;
      position: relative;
      transform: scale(1.0);
      transform-origin: bottom center;
      transition: transform 2s;

      &:hover {
        cursor: pointer;

        &:before {
          opacity: 1;
          top: -45px;
          visibility: visible;
        }
      }
    }

    img {
      align-items: center;
      bottom: 0;
      display: flex;
      justify-content: center;
      margin: 0 5px;
      position: relative;
      transform: scale(1);
      transform-origin: bottom center;
      transition: all 0.2s;
      width: 4em;

      &:hover {
        margin: 0 10px;
        transform: scale(1.2);
      }
    }
  }

  .jump {
    animation: JUMP 600ms 2 cubic-bezier(.4, 0.01, .6, .99);
  }

  @keyframes JUMP {
    0% {
      bottom: 0;
    }
    50% {
      bottom: 20px;
      padding-bottom: 20px;
    }
    100% {
      bottom: 0;
    }
  }

</style>
