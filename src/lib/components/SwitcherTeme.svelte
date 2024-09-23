<script>
  import { onMount } from 'svelte';

  let theme = 'light';
  const root = 'switcher'

  onMount(() => {
    const savedTheme = localStorage.getItem('theme');
    const prefersDark = window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches;

    theme = savedTheme ? savedTheme : prefersDark ? 'dark' : 'light';
    document.documentElement.setAttribute('data-theme', theme);
  });

  function toggleTheme() {
    theme = theme === 'light' ? 'dark' : 'light';
    document.documentElement.setAttribute('data-theme', theme);
    localStorage.setItem('theme', theme);
  }
</script>

<button type="button" class="switcher" on:click={toggleTheme}>
  <div class="switcher__inner">
    <div class="switcher__boll {theme == 'light' ? 'switcher__boll--left' : 'switcher__boll--right'}"></div>
  </div>
</button>
<!-- <button on:click={toggleTheme}>theme</button> -->

<style lang="scss">
  .switcher {
    &__inner {
      position: relative;
      width: 46px;
      background: red;
      height: 25px;
      border-radius: 50px;
    }

    &__boll {
      position: absolute;
      left: 0;
      top: 50%;
      transform: translateY(-50%);
      transition: 0.5s;
      height: 90%;
      aspect-ratio: 1/1;
      border-radius: 50%;
      background: blue;

      &--left {
        transform: translateY(-50%) translateX(10%);
      }

      &--right {
        left: 100%;
        transform: translateY(-50%) translateX(-110%);
      }
    }
  }
</style>