<script>
  export let defendant;

  function toggle() {
    let ssnArea = document.getElementById("ssnGroup");
    if (ssnArea.classList.contains("hidetext")) {
      ssnArea.classList.remove("hidetext");
    } else {
      ssnArea.classList.add("hidetext");
    }
  }
</script>

<style>
  .DefendantFooter > button {
    margin-left: 10px;
  }

  .hidetext {
    -webkit-text-security: disc; /* Default */
    cursor: pointer;
  }
</style>

<div class="table table-responsive">
  <table class="table table-striped table-dark">
    <thead>
      <tr>
        <th scope="col">First</th>
        <th scope="col">Last</th>
        <th scope="col">Middle</th>
        <th scope="col">DOB</th>
        <th scope="col">SSN</th>
        <th scope="col">Phone</th>
        <th scope="col">State</th>
        <th scope="col">City</th>
        <th scope="col">Address</th>
        <th scope="col">Postal Code</th>
        <th scope="col">Apt #</th>
      </tr>
    </thead>
    <tbody id="myTable">
      <tr>
        <td>{defendant.first}</td>
        <td>{defendant.last}</td>
        <td>{defendant.middle}</td>
        <td>{defendant.dob}</td>
        <td
          class="hidetext"
          id="ssnGroup"
          on:click={toggle}
          style="cursor:pointer;">
          {defendant.dependant_Ssn}
        </td>
        <td>{defendant.phone}</td>
        <td>{defendant.state}</td>
        <td>{defendant.city}</td>
        <td>{defendant.address}</td>
        <td>{defendant.postalCode}</td>
        <td>{defendant.aptNum}</td>
      </tr>
    </tbody>
  </table>
</div>
<div class="DefendantFooter" style="display:flex; justify-content:flex-end;">
  <button type="button" class="btn btn-primary">Edit</button>
  <button type="button" class="btn btn-danger">Delete</button>
</div>
