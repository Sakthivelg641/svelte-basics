<script>
  export let title;
  import Card from "./components/Card.svelte";
  import { DATA } from "../public/static/data";
</script>

<main>
  <h1>{title}</h1>
  <section class="grid-container">
    {#each DATA as data}
      <Card heading={data.heading} order={data.order} color={data.color} />
    {/each}
  </section>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }

  .grid-container {
    display: grid;
    grid-template-columns: auto auto auto auto auto auto;
    justify-content: center;
    grid-gap: 2rem;
  }

  /* Extra small devices (phones, 600px and down) */
  @media only screen and (max-width: 600px) {
    .grid-container {
      display: grid;
      grid-template-columns: auto;
    }
  }

  /* Small devices (portrait tablets and large phones, 600px and up) */
  @media only screen and (min-width: 600px) {
    .grid-container {
      display: grid;
      grid-template-columns: auto;
    }
  }

  /* Medium devices (landscape tablets, 768px and up) */
  @media only screen and (min-width: 768px) {
    .grid-container {
      display: grid;
      grid-template-columns: auto auto;
    }
  }

  /* Large devices (laptops/desktops, 992px and up) */
  @media only screen and (min-width: 992px) {
    .grid-container {
      display: grid;
      grid-template-columns: auto auto auto;
    }
  }

  /* Extra large devices (large laptops and desktops, 1200px and up) */
  @media only screen and (min-width: 1200px) {
    .grid-container {
      display: grid;
      grid-template-columns: auto auto auto auto;
    }
  }
</style>
