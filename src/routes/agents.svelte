<script>
  let tableDataAgents = [
    {
      name: "John Doe",
      phone: "555-555-5555",
      agency: "NYC Bail",
      bonds: ["filler", "filler", "filler", "filler", "filler", "filler"]
    },
    {
      name: "Jane Smith",
      phone: "888-999-1010",
      agency: "San Fran Bail",
      bonds: ["filler", "filler", "filler"]
    },
    {
      name: "Elvis Presley",
      phone: "123-456-789",
      agency: "Texas",
      bonds: ["filler", "filler"]
    }
  ];

  let listAgents = [];
  let searchQueryAgents;

  $: searchQueryAgents
    ? (listAgents = tableDataAgents.filter(({ name, phone, agency }) => {
        return (
          name.toLowerCase().indexOf(searchQueryAgents.toLowerCase()) !== -1 ||
          phone.toLowerCase().indexOf(searchQueryAgents.toLowerCase()) !== -1 ||
          agency.toLowerCase().indexOf(searchQueryAgents.toLowerCase()) !== -1
        );
      }))
    : (listAgents = tableDataAgents);
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
  <title>Agents</title>
</svelte:head>
<h3>
  Agents
  <span class="badge badge-primary">{tableDataAgents.length}</span>
</h3>
<div class="input-group mb-3">
  <input
    type="text"
    class="form-control"
    placeholder="Search for a Defendant"
    aria-label="Defendant's Name"
    aria-describedby="basic-addon2"
    id="myInput"
    bind:value={searchQueryAgents} />
</div>
<button
  type="button"
  class="btn btn-primary btn-lg btn-block"
  style="margin-bottom: 10px">
  Add New Agent
</button>
<div class="table table-responsive">
  <table class="table table-striped table-dark">
    <thead>
      <tr>

        <th scope="col">Name</th>
        <th scope="col">Phone</th>
        <th scope="col">Agency</th>
        <th scope="col">Bonds</th>
        <th scope="col">Details</th>
      </tr>
    </thead>

    <tbody id="myTable">
      {#each listAgents as agent}
        <tr>
          <td>{agent.name}</td>
          <td>{agent.phone}</td>
          <td>{agent.agency}</td>
          <td>{agent.bonds.length}</td>
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
