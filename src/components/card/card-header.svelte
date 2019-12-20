<script>
  export let text = "";
</script>

<style>
  .card-header {
    border-bottom: 1px dashed #333;
  }
</style>

<div class="card-header">
  <h4>{text || 'default'}</h4>
</div>
