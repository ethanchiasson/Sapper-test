<script>
  import Nav from "../components/Nav.svelte";

  export let segment;
</script>

<style>
  main {
    position: relative;
    /* max-width: 56em; */
    background-color: white;
    padding: 2em;
    box-sizing: border-box;
    background-color: white;
    min-height: calc(100vh - 4em - 1px);
  }
</style>

<Nav {segment} />
<main>
  <slot />
</main>
