<script>
  export let heading, color, order;
  import { DATA } from "../../public/static/data";

  let description = "";

  const getDetails = () => {
    DATA.map((i, j) => {
      if (i.order === order) {
        description = i.description;
      }
    });
  };
</script>

<div class="card" style="--color: {color}" on:click={getDetails}>
  <div class="grid-container-1">
    <h2>{order}</h2>
    <h3>{heading}</h3>
  </div>
  <p>{description}</p>
</div>

<style>
  .card {
    box-shadow: 0 0.5rem 1rem 0 rgba(0, 0, 0, 0.2);
    background-color: var(--color);
    border-radius: 4px;
    color: white;
    cursor: pointer;
    font-size: 0.875rem;
    height: 15rem;
    width: 18rem;
    padding: 1rem;
    text-align: left;
    margin-bottom: 2rem;
  }
  h2 {
    display: inline-block;
    font-size: 3rem;
    padding-bottom: -1rem;
    opacity: 0.5;
  }
  h3 {
    font-size: 1.5rem;
    font-weight: bold;
    padding-top: 1.5rem;
  }
  .grid-container-1 {
    display: grid;
    grid-template-columns: auto auto;
    grid-gap: 1rem;
  }
</style>
