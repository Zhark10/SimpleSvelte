<script>
  async function getUserAsync() {
    let response = await fetch(`https://swapi.co/api/people/1/`);
    let data = await response.json();
    return data;
  }

  getUserAsync().then(data => console.log(data));
</script>

<h1>Home</h1>
<p>Welcome to my website</p>

