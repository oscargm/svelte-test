<script>
  const colors = {
    primary: "#2759b8",
    secondary: "#27b82e",
    warning: "#b82727",
    reset: "white"
  };
  function handleClick(buttonType) {
    console.log("handleClick", buttonType);
    document.querySelectorAll(".card-body").forEach(card => {
      card.style.background = colors[buttonType];
    });
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
  .card-header {
    border-bottom: 1px dashed #333;
  }
  .card-body {
    text-align: justify;
  }
  .card-footer {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    border-top: 1px dashed #333;
    padding-top: 1rem;
  }
  button.primary {
    background-color: #2759b8;
    color: white;
  }
  button.secondary {
    background-color: #27b82e;
    color: white;
  }
  button.warning {
    background-color: #b82727;
    color: white;
  }
</style>

<div class="card-wrapper">
  <div class="card">
    <div class="card-header">
      <h4>Card Title</h4>
    </div>
    <div class="card-body">
      <p>
        Lorem Ipsum is simply dummy text of the printing and typesetting
        industry. Lorem Ipsum has been the industry's standard dummy text ever
        since the 1500s, when an unknown printer took a galley of type and
        scrambled it to make a type specimen book. It has survived not only five
        centuries, but also the leap into electronic typesetting, remaining
        essentially unchanged. It was popularised in the 1960s with the release
        of Letraset sheets containing Lorem Ipsum passages, and more recently
        with desktop publishing software like Aldus PageMaker including versions
        of Lorem Ipsum.
      </p>
    </div>
    <div class="card-footer">
      <button class="primary" on:click={() => handleClick('primary')}>
        Primary
      </button>
      <button class="secondary" on:click={() => handleClick('secondary')}>
        Secondary
      </button>
      <button class="warning" on:click={() => handleClick('warning')}>
        Warning
      </button>
      <button class="reset" on:click={() => handleClick('reset')}>Reset</button>
    </div>
  </div>
</div>
