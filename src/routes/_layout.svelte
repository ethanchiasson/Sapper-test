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
    background-color: red;
    width: 100vw;
    height: 100vh;
  }
</style>

<Nav {segment} />
<main>
  <slot />
</main>
