<script>
  export let index;
  export let text;
  export let closeAction;
</script>

<style>
  .card-header {
    position: relative;
    border-bottom: 1px dashed #333;
  }
  .card-close {
    position: absolute;
    top: 0px;
    right: 0px;
    width: 55px;
    background-color: #eee;
    padding: 0.3rem;
    cursor: pointer;
  }
</style>

<div class="card-header">
  <span class="card-close" on:click={() => closeAction(index)}>Close</span>
  <h4>{text || 'default'}</h4>
</div>
