<script>
  export let name;
  export let defendant;
  export let agents;
</script>

<style>
  .modal-content {
    color: #333;
  }
</style>

<!-- Button trigger modal -->
<button
  type="button"
  class="btn btn-primary d-flex justify-content-center"
  data-toggle="modal"
  data-target="#exampleModal2"
  style="float: right; margin-bottom: 2vh">
  Add Bond
  <span class="material-icons">add</span>
</button>
<div class="table table-responsive">
  <table class="table table-striped table-dark">
    <thead>
      <tr>
        <th scope="col">Power #</th>
        <th scope="col">Status</th>
        <th scope="col">Agency</th>
        <th scope="col">Agent</th>
        <th scope="col">Amount</th>
        <th scope="col">Posted Date</th>
        <th scope="col">Forfiture By</th>
        <th scope="col">Actions</th>
      </tr>
    </thead>
    <tbody id="myTable">
      {#each defendant.bonds as bonds}
        <tr>
          <td>{bonds.power_Number}</td>
          <td>{bonds.status}</td>
          <td>{bonds.agency}</td>
          <td>{bonds.agent}</td>
          <td>${bonds.amount}</td>
          <td>{bonds.posted_Date}</td>
          <td>{bonds.forfiture_By}</td>
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
            <button
              type="button"
              class="btn btn-sm btn-primary"
              style="margin: 2px">
              View
            </button>
          </td>
        </tr>
      {/each}
    </tbody>
  </table>
</div>

<!-- Modal -->
<div
  class="modal fade"
  id="exampleModal2"
  tabindex="-1"
  role="dialog"
  aria-labelledby="exampleModalLabel"
  aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">
          New Bond for Defendant {name}
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
            <label for="exampleFormControlInput1">Amount</label>
            <input
              type="number"
              min="1"
              class="form-control"
              id="exampleFormControlInput1"
              placeholder="Enter the Payment Amount as seen on Invoice" />
          </div>
          <div class="form-group">
            <label for="paymentSelect">Payment Type</label>
            <select class="form-control" id="paymentSelect">
              <option>PayPal</option>
              <option>Cash</option>
              <option>Check</option>
              <option>Credit Card</option>
            </select>
          </div>
          <div class="form-group">
            <label for="agentSelect">Ageny</label>
            <select class="form-control" id="agentSelect">
              <option>US Bail</option>
              <option>NYC Bail</option>
              <option>San Fran Bail</option>
            </select>
            <label for="agentSelect">Agent</label>
            <select class="form-control" id="agentSelect">
              {#each agents.names as agent}
                <option>{agent.agent_name}</option>
              {/each}
            </select>
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
