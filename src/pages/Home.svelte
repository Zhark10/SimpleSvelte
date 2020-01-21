<script>
  let promise = getLuke();
  
  async function getLuke() {
    let response = await fetch(`https://swapi.co/api/people/1/`);
    let data = await response.json();
    return data.name;
  }
  function onClick() {
    promise = getLuke();
  }
</script>

<h1>Home</h1>
<button on:click={onClick}>get jedi</button>
{#await promise}
  <p>...waiting</p>
{:then name}
  <p>Here was {name}</p>
{/await}
