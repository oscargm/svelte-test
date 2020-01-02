<script>
  import Header from "./card-header.svelte";
  import Body from "./card-body.svelte";
  import Footer from "./card-footer.svelte";

  export let index;
  export let closeAction;

  const actions = [
    {
      id: 0,
      type: "primary",
      onClickAction: handleClick,
      text: "Primary"
    },
    {
      id: 1,
      type: "secondary",
      onClickAction: handleClick,
      text: "Secondary"
    },
    {
      id: 2,
      type: "warning",
      onClickAction: handleClick,
      text: "Warning"
    },
    {
      id: 3,
      type: "reset",
      onClickAction: handleClick,
      text: "Reset"
    }
  ];
  const colors = {
    primary: { background: "#2759b8", color: "white" },
    secondary: { background: "#27b82e", color: "black" },
    warning: { background: "#b82727", color: "white" },
    reset: { background: "white", color: "black" }
  };

  const setCardBodyBackgroundColor = buttonType => {
    let card = document
      .getElementById(`card-${index}`)
      .querySelector(".card-body");

    card.style.background = colors[buttonType].background;
    card.style.color = colors[buttonType].color;
  };

  function handleClick(buttonType) {
    setCardBodyBackgroundColor(buttonType);
  }
</script>

<style>
  .card-wrapper {
    width: 25rem;
    padding: 1rem;
  }
  .card {
    display: flex;
    flex-direction: column;
    padding: 1rem;

    border: 1px solid black;
    border-radius: 5px;
    box-shadow: #333 10px 10px 10px 3px;
  }
</style>

<div class="card-wrapper" id={`card-${index}`}>
  <div class="card">
    <Header text={`${index} -. Click on the buttons`} {closeAction} {index} />
    <Body
      text={"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum."} />
    <Footer {actions} />
  </div>
</div>
