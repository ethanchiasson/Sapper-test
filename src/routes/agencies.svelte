<script>
  let tableDataAgencies = [
    {
      name: "NYC Bail",
      phone: "555-555-5555",
      state: "New York",
      city: "Ney York",
      address: "1234 NYC Drive",
      agents: ["filler", "filler", "filler", "filler", "filler", "filler"]
    },
    {
      name: "San Fran Bail",
      phone: "222-3333-4444",
      state: "California",
      city: "San Francisco",
      address: "54321 Golden Gate Lane",
      agents: [
        "filler",
        "filler",
        "filler",
        "filler",
        "filler",
        "filler",
        "filler",
        "filler"
      ]
    },
    {
      name: "Texas Bail",
      phone: "777-888-9999",
      state: "Texas",
      city: "Houston",
      address: "999 Rockets Ave",
      agents: ["filler", "filler", "filler", "filler"]
    }
  ];

  let listAgencies = [];
  let searchQueryAgencies;

  $: searchQueryAgencies
    ? (listAgencies = tableDataAgencies.filter(
        ({ name, phone, state, city, address }) => {
          return (
            name.toLowerCase().indexOf(searchQueryAgencies.toLowerCase()) !==
              -1 ||
            phone.toLowerCase().indexOf(searchQueryAgencies.toLowerCase()) !==
              -1 ||
            state.toLowerCase().indexOf(searchQueryAgencies.toLowerCase()) !==
              -1 ||
            city.toLowerCase().indexOf(searchQueryAgencies.toLowerCase()) !==
              -1 ||
            address.toLowerCase().indexOf(searchQueryAgencies.toLowerCase()) !==
              -1
          );
        }
      ))
    : (listAgencies = tableDataAgencies);
</script>

<style>
  .viewButton {
    width: 75px;
    height: auto;
    background-color: #333;
    border: none;
    border-radius: 5px;
  }

  .viewButton:hover {
    background-color: rgb(13, 146, 255);
  }

  .viewButton:hover > .material-icons {
    color: white;
  }

  .material-icons {
    display: inline-flex;
    vertical-align: top;
  }
</style>

<svelte:head>
  <title>Agencies</title>
</svelte:head>
<h3>
  Agencies
  <span class="badge badge-primary">{tableDataAgencies.length}</span>
</h3>
<div class="input-group mb-3">
  <input
    type="text"
    class="form-control"
    placeholder="Search for a Defendant"
    aria-label="Defendant's Name"
    aria-describedby="basic-addon2"
    id="myInput"
    bind:value={searchQueryAgencies} />
</div>
<button
  type="button"
  class="btn btn-primary btn-lg btn-block"
  style="margin-bottom: 10px">
  Add New Agency
</button>
<div class="table table-responsive">
  <table class="table table-striped table-dark">
    <thead>
      <tr>

        <th scope="col">Name</th>
        <th scope="col">Phone</th>
        <th scope="col">State</th>
        <th scope="col">City</th>
        <th scope="col">Address</th>
        <th scope="col">Agents</th>
        <th scope="col">Details</th>
      </tr>
    </thead>

    <tbody id="myTable">
      {#each listAgencies as agency}
        <tr>
          <td>{agency.name}</td>
          <td>{agency.phone}</td>
          <td>{agency.state}</td>
          <td>{agency.city}</td>
          <td>{agency.address}</td>
          <td>{agency.agents.length}</td>
          <td>
            <button class="viewButton">
              <span class="material-icons">remove_red_eye</span>
            </button>
          </td>
        </tr>
      {/each}
    </tbody>
  </table>
</div>
