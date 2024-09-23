<script>
  import Menu from "$lib/components/Menu.svelte";
</script>

<div class="wrapper">
  <Menu />
  <main class="main">
    <slot/>
  </main>
</div>

<style lang="scss">
  .wrapper {
    display: flex;
  }
</style>

