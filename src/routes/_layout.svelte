<script>
  import Nav from "../components/Nav.svelte";

  export let segment;
</script>

<style>
  main {
    position: relative;
    /* max-width: 56em; */
    color: white;
    background-color: #1a202c;
    padding: 2em;
    box-sizing: border-box;
    min-height: calc(100vh - 4em - 1px);
  }
</style>

<Nav {segment} />
<main>
  <slot />
</main>
