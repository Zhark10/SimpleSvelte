<script>
  let promise = getLuke();

  function getRandomId(max) {
    return Math.floor(Math.random() * Math.floor(max));
  }

  async function getLuke() {
    let id = getRandomId(5);
    let response = await fetch(`https://swapi.co/api/people/${id}/`);
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
