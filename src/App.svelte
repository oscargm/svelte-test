<script>
  export let name;
  import Card from "./components/card/card.svelte";
</script>

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
  .card-wrapper {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
  }
  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <h1>Hello {name}!</h1>
  <p>
    Visit the
    <a href="https://svelte.dev/tutorial">Svelte tutorial</a>
    to learn how to build Svelte apps.
  </p>
  <div class="card-wrapper">
    {#each Array(8) as _, i}
      <Card index={i} />
    {/each}
  </div>
</main>
