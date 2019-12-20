<script>
  export let actions = [];
</script>

<style>
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

<div class="card-footer">
  {#each actions as { id, type, onClickAction, text }}
    <button class={type} on:click={() => onClickAction(type)}>{text}</button>
  {/each}
</div>
