<script>
  export let name;
  import Card from "./components/card/card.svelte";
  let cards = [1, 2, 3, 4, 5, 6, 7, 8];
  const deleteCard = card => {
    console.log("delete card", cards);
    let removed = cards.splice(cards.indexOf(card), 1);
    console.log("removed", removed);
    cards = cards;
    console.log("cards after", cards);
  };
  const addCard = () => {
    cards = cards.concat(cards.length);
    console.log(cards);
  };
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
  .wrapper {
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
  <div>
    <button on:click={() => addCard()}>Add a Card</button>
    <span>{cards.length}</span>
  </div>
  <div class="wrapper">
    {#each cards as card, i}
      <Card index={card} closeAction={deleteCard} />
    {/each}
  </div>
</main>
