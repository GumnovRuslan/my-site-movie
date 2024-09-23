<script>
  import SwitcherTeme from "./SwitcherTeme.svelte";
</script>

<section class="menu">
  <div class="menu__inner">
    <nav class="menu__nav_list">
      <a href="#" class="menu__nav_item">Home</a>
      <SwitcherTeme/>
    </nav>
  </div>
</section>

<style lang="scss">
  .menu {
    width: 400px;
    height: 100vh;
    background: var(--text-color);
  }
</style>