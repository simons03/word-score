<script>
    import "../app.css"
</script>


<slot />


<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    .btn {
    @apply font-bold py-2 px-4 rounded;
  }
  .btn-blue {
    @apply bg-blue-500 text-white;
  }
  .btn-blue:hover {
    @apply bg-blue-700;
  }
</style>