<script lang="ts">
  import Weather from "./components/Weather.svelte";
</script>

<main style="text-align: center;">
  <h1 class="fs-1">Aplicación del Clima</h1>
  <hr />
  <Weather />
</main>

<style>
  main {
    background-color: rgb(236, 236, 236);
  }
  .fs-1 {
    background-color: rgb(218, 64, 116);
    color: rgb(255, 255, 255);
  }
</style>
