<script>
  export let text;
  export let clickHandler;
</script>

<button on:click={clickHandler}>{text}</button>

<style>
  button {
    background-color: black;
    color: white;
    border-radius: none;
    border: none;
    cursor: pointer;
  }
</style>