<script>
  // jQuery(document).ready(function() {
  //   jQuery("#myInput").on("keyup", function() {
  //     var value = jQuery(this)
  //       .val()
  //       .toLowerCase();
  //     jQuery("#myTable tr").filter(function() {
  //       jQuery(this).toggle(
  //         jQuery(this)
  //           .text()
  //           .toLowerCase()
  //           .indexOf(value) > -1
  //       );
  //     });
  //   });
  // });

  let tableData = [
    {
      First: "John",
      Last: "Doe",
      Posted_date: "9/10/15",
      Power_Number: "11234",
      Agency: "SouthSide Bail"
    },
    {
      First: "Joe",
      Last: "Danger",
      Posted_date: "9/10/15",
      Power_Number: "11234",
      Agency: "Gator Bail"
    },
    {
      First: "Jane",
      Last: "White",
      Posted_date: "9/10/15",
      Power_Number: "11234",
      Agency: "Gator Bail"
    },
    {
      First: "Ethan",
      Last: "Black",
      Posted_date: "9/10/15",
      Power_Number: "11234",
      Agency: "Hub City Bail Bonds"
    },
    {
      First: "Joshua",
      Last: "Hernendez",
      Posted_date: "9/10/15",
      Power_Number: "11234",
      Agency: "US Bail"
    },
    {
      First: "Jimmy",
      Last: "Hendrick",
      Posted_date: "9/10/15",
      Power_Number: "11234",
      Agency: "SouthSide Bail"
    },
    {
      First: "Max",
      Last: "Ammillion",
      Posted_date: "9/10/15",
      Power_Number: "11234",
      Agency: "Hub City Bail Bonds"
    },
    {
      First: "Rich",
      Last: "Gunt",
      Posted_date: "9/10/15",
      Power_Number: "11234",
      Agency: "Hub City Bail Bonds"
    },
    {
      First: "Jake",
      Last: "Swanson",
      Posted_date: "9/10/15",
      Power_Number: "11234",
      Agency: "Gator Bail"
    },
    {
      First: "Ezra",
      Last: "Chase",
      Posted_date: "9/10/15",
      Power_Number: "11234",
      Agency: "SouthSide Bail"
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
  <!-- <div class="input-group-append">
    <button class="btn btn-primary" type="button">Button</button>
  </div> -->
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
        <th scope="col">Power #</th>
        <th scope="col">First</th>
        <th scope="col">Last</th>
        <th scope="col">Posted Date</th>
        <th scope="col">Agency</th>
        <th scope="col">View Defendant</th>
      </tr>
    </thead>

    <tbody id="myTable">
      {#each list as defendant}
        <tr>
          <td>{defendant.Power_Number}</td>
          <td>{defendant.First}</td>
          <td>{defendant.Last}</td>
          <td>{defendant.Posted_date}</td>
          <td>{defendant.Agency}</td>
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
