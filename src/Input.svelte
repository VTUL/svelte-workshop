<script>
  import { highlightedName } from './stores.js'
  let highlight = "Leanne Graham"
</script>

<div>
  <label for="highlighted-name">Name to Highlight:</label>
  <input name="highlighted-name" bind:value={$highlightedName} />
  <h2>Pay attention to this person: {$highlightedName}</h2>
</div>