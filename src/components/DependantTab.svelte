<script>
  export let defendant;
  export let name;

  function toggle() {
    let ssnAreaDEP = document.getElementById("ssnDEP");
    if (ssnAreaDEP.classList.contains("hidetext")) {
      ssnAreaDEP.classList.remove("hidetext");
    } else {
      ssnAreaDEP.classList.add("hidetext");
    }
  }
</script>

<style>
  .hidetext {
    -webkit-text-security: disc; /* Default */
    cursor: pointer;
  }
  .modal-content {
    color: #333;
  }
</style>

<button
  type="button"
  class="btn btn-primary d-flex justify-content-center"
  data-toggle="modal"
  data-target="#exampleModal3"
  style="float: right; margin-bottom: 2vh">
  Add Dependant
  <span class="material-icons">add</span>
</button>
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
        <th scope="col">Postal Code</th>
        <th scope="col">Address</th>
        <th scope="col">Apt #</th>
        <th scope="col">Actions</th>
      </tr>
    </thead>
    <tbody id="myTable">
      <tr>
        <td>{defendant.dependant_First}</td>
        <td>{defendant.dependant_Last}</td>
        <td>{defendant.dependant_Middle}</td>
        <td>{defendant.dependant_Dob}</td>
        <td
          class="hidetext"
          id="ssnDEP"
          on:click={toggle}
          style="cursor:pointer;">
          {defendant.dependant_Ssn}
        </td>
        <td>{defendant.dependant_Phone}</td>
        <td>{defendant.dependant_State}</td>
        <td>{defendant.dependant_City}</td>
        <td>{defendant.dependant_Address}</td>
        <td>{defendant.dependant_PostalCode}</td>
        <td>{defendant.dependant_AptNum}</td>
        <td>
          <button
            type="button"
            class="btn btn-sm btn-secondary"
            style="margin: 2px">
            Edit
          </button>
          <button
            type="button"
            class="btn btn-sm btn-danger"
            style="margin: 2px">
            Delete
          </button>
        </td>
      </tr>
    </tbody>
  </table>
</div>

<!-- Modal -->
<div
  class="modal fade"
  id="exampleModal3"
  tabindex="-1"
  role="dialog"
  aria-labelledby="exampleModalLabel"
  aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">
          Add New Dependant for {name}
        </h5>
        <button
          type="button"
          class="close"
          data-dismiss="modal"
          aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <form>
          <div class="form-group">
            <label for="exampleFormControlInput1">First Name</label>
            <input
              type="text"
              class="form-control"
              id="exampleFormControlInput1"
              placeholder="First Name" />
            <label for="exampleFormControlInput1">Middle Name</label>
            <input
              type="text"
              class="form-control"
              id="exampleFormControlInput1"
              placeholder="Middle Name" />
            <label for="exampleFormControlInput1">Last Name</label>
            <input
              type="text"
              class="form-control"
              id="exampleFormControlInput1"
              placeholder="Last Name" />
            <label for="exampleFormControlInput1">DOB</label>
            <input
              type="date"
              class="form-control"
              id="exampleFormControlInput1"
              placeholder="Last Name" />
            <label for="exampleFormControlInput1">SSN</label>
            <input
              type="number"
              class="form-control"
              id="exampleFormControlInput1"
              placeholder="Social Security Number" />
            <label for="exampleFormControlInput1">State</label>
            <input
              type="text"
              class="form-control"
              id="exampleFormControlInput1"
              placeholder="State" />
            <label for="exampleFormControlInput1">City</label>
            <input
              type="text"
              class="form-control"
              id="exampleFormControlInput1"
              placeholder="City" />
            <label for="exampleFormControlInput1">Zip Code</label>
            <input
              type="text"
              class="form-control"
              id="exampleFormControlInput1"
              placeholder="ZIP" />
            <label for="exampleFormControlInput1">Phone Number</label>
            <input
              type="text"
              class="form-control"
              id="exampleFormControlInput1"
              placeholder="Phone Number" />
            <label for="exampleFormControlInput1">Email</label>
            <input
              type="email"
              class="form-control"
              id="exampleFormControlInput1"
              placeholder="Phone Number" />
          </div>
        </form>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">
          Cancel
        </button>
        <button type="button" class="btn btn-primary">
          Create Payment Record
        </button>
      </div>
    </div>
  </div>
</div>
