<script>
  const defendants = [
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

  jQuery(document).ready(function() {
    jQuery("#myInput").on("keyup", function() {
      var value = jQuery(this)
        .val()
        .toLowerCase();
      jQuery("#myTable tr").filter(function() {
        jQuery(this).toggle(
          jQuery(this)
            .text()
            .toLowerCase()
            .indexOf(value) > -1
        );
      });
    });
  });
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

<div class="input-group mb-3">
  <input
    type="text"
    class="form-control"
    placeholder="Search for a Defendant"
    aria-label="Defendant's Name"
    aria-describedby="basic-addon2"
    id="myInput" />
  <div class="input-group-append">
    <button class="btn btn-primary" type="button">Button</button>
  </div>
</div>
<button
  type="button"
  class="btn btn-primary btn-lg btn-block"
  style="margin-bottom: 10px">
  Add New Defendant
</button>
<div class="table-responsive">
  <table class="table table-dark">
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
    {#each defendants as defendant}
      <tbody id="myTable">
        <tr>
          <th scope="row">{defendant.Power_Number}</th>
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
      </tbody>
    {/each}
  </table>
</div>
