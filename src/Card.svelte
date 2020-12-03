<script>
  export let entry;
  export let passedName;
</script>

<section class="{passedName === entry.name ? 'highlight' : ''}">
  <h1>{entry.name}</h1>
  <div>
    <ul>
      <li>Username: {entry.username}</li>
      <li>Email: {entry.email}</li>
    </ul>
  </div>
</section>

<style>
  section {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    text-align: left;
    border: 1px gray solid;
    max-width: 33%;
    width: auto;
    padding: 1em;
    margin: .5em;
    min-width: 18%;
  }

  h1 {
    width: 100%;
    text-align: center;
  }

  .highlight {
    border: 2px red solid;
  }
</style>