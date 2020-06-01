<script>
  let tableData = [
    {
      First: "John",
      Last: "Doe",
      Posted_date: "9/10/15",
      Power_Number: "FN1212",
      Agency: "NYC Bail"
    },
    {
      First: "Joe",
      Last: "Danger",
      Posted_date: "7/11/15",
      Power_Number: "FN3434",
      Agency: "Texas Bail"
    },
    {
      First: "Jane",
      Last: "White",
      Posted_date: "9/10/15",
      Power_Number: "FN5656",
      Agency: "NYC Bail"
    },
    {
      First: "Ethan",
      Last: "Black",
      Posted_date: "7/7/09",
      Power_Number: "FN7878",
      Agency: "San Fran Bail"
    },
    {
      First: "Joshua",
      Last: "Hernendez",
      Posted_date: "8/12/20",
      Power_Number: "FN9109",
      Agency: "NYC Bail"
    },
    {
      First: "Jimmy",
      Last: "Hendrick",
      Posted_date: "9/10/15",
      Power_Number: "FN1122",
      Agency: "Texas Bail"
    },
    {
      First: "Max",
      Last: "Ammillion",
      Posted_date: "6/6/19",
      Power_Number: "FN2233",
      Agency: "Texas Bail"
    },
    {
      First: "Rich",
      Last: "Gunt",
      Posted_date: "12/9/19",
      Power_Number: "FN4455",
      Agency: "San Fran Bail"
    },
    {
      First: "Jake",
      Last: "Swanson",
      Posted_date: "9/10/15",
      Power_Number: "FN6677",
      Agency: "NYC Bail"
    },
    {
      First: "Ezra",
      Last: "Chase",
      Posted_date: "9/10/15",
      Power_Number: "FN8899",
      Agency: "NYC Bail"
    }
  ];

  let list = [];
  let searchQuery;

  $: searchQuery
    ? (list = tableData.filter(
        ({ First, Last, Posted_date, Power_Number, Agency }) => {
          return (
            First.toLowerCase().indexOf(searchQuery.toLowerCase()) !== -1 ||
            Last.toLowerCase().indexOf(searchQuery.toLowerCase()) !== -1 ||
            Posted_date.toLowerCase().indexOf(searchQuery.toLowerCase()) !==
              -1 ||
            Power_Number.toLowerCase().indexOf(searchQuery.toLowerCase()) !==
              -1 ||
            Agency.toLowerCase().indexOf(searchQuery.toLowerCase()) !== -1
          );
        }
      ))
    : (list = tableData);
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
  <title>Defendants</title>
</svelte:head>
<h3>
  Defendants
  <span class="badge badge-primary">{tableData.length}</span>
</h3>
<div class="input-group mb-3">
  <input
    type="text"
    class="form-control"
    placeholder="Search for a Defendant"
    aria-label="Defendant's Name"
    aria-describedby="basic-addon2"
    id="myInput"
    bind:value={searchQuery} />
</div>
<button
  type="button"
  class="btn btn-primary btn-lg btn-block"
  style="margin-bottom: 10px">
  Add New Defendant
</button>
<div class="table table-responsive">
  <table class="table table-striped table-dark">
    <thead>
      <tr>

        <th scope="col">First</th>
        <th scope="col">Last</th>
        <th scope="col">Posted Date</th>
        <th scope="col">Agency</th>
        <th scope="col">Power #</th>
        <th scope="col">Details</th>
      </tr>
    </thead>

    <tbody id="myTable">
      {#each list as defendant}
        <tr>
          <td>{defendant.First}</td>
          <td>{defendant.Last}</td>
          <td>{defendant.Posted_date}</td>
          <td>{defendant.Agency}</td>
          <td>{defendant.Power_Number}</td>
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
