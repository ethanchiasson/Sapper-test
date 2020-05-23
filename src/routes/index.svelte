<script>
  const defendants = [
    { First: "John", Last: "Manager", Posted_date: "9/10/15" },
    { First: "Joe", Last: "Manager", Posted_date: "9/10/15" },
    { First: "Jane", Last: "Manager", Posted_date: "9/10/15" },
    { First: "Ethan", Last: "Manager", Posted_date: "9/10/15" },
    { First: "Joshua", Last: "Manager", Posted_date: "9/10/15" },
    { First: "Jimmy", Last: "Manager", Posted_date: "9/10/15" },
    { First: "Max", Last: "Manager", Posted_date: "9/10/15" },
    { First: "Rich", Last: "Manager", Posted_date: "9/10/15" },
    { First: "Jake", Last: "Manager", Posted_date: "9/10/15" },
    { First: "Ezra", Last: "Manager", Posted_date: "9/10/15" }
  ];
</script>

<style>
  .container {
    display: flex;
    flex-direction: column;
  }
  .defendant {
    background-color: #212121;
    color: white;
    padding: 10px;
    flex: 1;
    min-width: 90%;
    max-width: 100%;
    margin: auto;
    margin-bottom: 10px;
  }

  button {
    width: 75px;
    height: auto;
    background-color: #333;
    border: none;
    border-radius: 5px;
  }

  button:hover {
    background-color: rgb(13, 146, 255);
  }

  button:hover > .material-icons {
    color: white;
  }
</style>

<svelte:head>
  <title>Defendants</title>
</svelte:head>

<div class="container">
  {#each defendants as defendant}
    <div class="defendant">
      <div class="card" style="display: flex">
        <h1 style="flex:3">{defendant.First} {defendant.Last}</h1>
        <p style="flex:1">{defendant.Posted_date}</p>
        <button>
          <span class="material-icons">remove_red_eye</span>
        </button>
      </div>
    </div>
  {/each}
</div>
