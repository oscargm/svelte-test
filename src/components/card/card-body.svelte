<script>
  export let text = "";
</script>

<style>
  .card-body {
    text-align: justify;
    transition: background-color 0.5s ease;
    transition: color 0.5s ease;
    padding: 0.5rem;
  }
</style>

<div class="card-body">
  <p>{text || 'default'}</p>
</div>
