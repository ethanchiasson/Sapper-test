<script>
  let defendant = {
    power_Number: "7777",
    first: "John",
    middle: "Michael",
    last: "Doe",
    dob: "5/5/1995",
    status: "Forfiture",
    balance: "4,000",
    address: "555 Sunny Lane",
    phone: "555-555-5555",
    ssn: "555-55-5555",
    city: "Houston",
    state: "Texas",
    postalCode: "90507",
    aptNum: "444",
    dependant_First: "Jane",
    dependant_Middle: "Anne",
    dependant_Last: "Doe",
    dependant_Dob: "4/4/1994",
    dependant_Address: "555 Sunny Lane",
    dependant_Phone: "999-555-5555",
    dependant_Ssn: "555-555-555",
    dependant_City: "Austin",
    dependant_State: "Texas",
    dependant_PostalCode: "90555",
    dependant_AptNum: "1234",
    agency: "Gator Bail",
    bonds: [
      {
        status: "paid",
        power_Number: "12345",
        agent: "Tony Hawk",
        agency: "Gator Bail",
        amount: "4000",
        posted_Date: "4/4/2014",
        forfiture_By: "7/7/2015"
      },
      {
        status: "Forfiture",
        power_Number: "565656",
        agent: "Alex Joe",
        agency: "West Side Bail",
        amount: "10000",
        posted_Date: "4/4/2018",
        forfiture_By: "7/7/2018"
      }
    ]
  };
</script>

<style>
  .container {
    width: 100%;
    margin: auto;
    /* background-color: lightskyblue; */
  }
  .defendantHeader,
  .defendantTabs {
    width: 100%;
  }

  .defendantTabs {
    margin-top: 2vh;
  }
</style>

<svelte:head>
  <title>Defendant - {defendant.name}</title>
</svelte:head>

<div class="container">
  <div class="defendantHeader" style="display:flex">
    <div class="left" style="flex:2">
      <h3>{defendant.first} {defendant.middle} {defendant.last}</h3>
      <span class="badge badge-pill badge-danger">{defendant.status}</span>
      <span class="badge badge-pill badge-secondary">{defendant.agency}</span>
    </div>
    <div class="right" style="flex:1">
      <button type="button" class="btn btn-success" style="float:right">
        <h4>
          Balance
          <span class="badge badge-light">${defendant.balance}</span>
        </h4>
      </button>
    </div>
  </div>
  <!--  -->
  <!--  -->
  <!--  -->
  <div class="defendantTabs">
    <ul class="nav nav-pills mb-3" id="pills-tab" role="tablist">
      <li class="nav-item" role="presentation">
        <a
          class="nav-link active"
          id="pills-home-tab"
          data-toggle="pill"
          href="#pills-home"
          role="tab"
          aria-controls="pills-home"
          aria-selected="true">
          {defendant.first} {defendant.last}
        </a>
      </li>
      <li class="nav-item" role="presentation">
        <a
          class="nav-link"
          id="pills-profile-tab"
          data-toggle="pill"
          href="#pills-profile"
          role="tab"
          aria-controls="pills-profile"
          aria-selected="false">
          Dependant
        </a>
      </li>
      <li class="nav-item" role="presentation">
        <a
          class="nav-link"
          id="pills-contact-tab"
          data-toggle="pill"
          href="#pills-contact"
          role="tab"
          aria-controls="pills-contact"
          aria-selected="false">
          Bonds
        </a>
      </li>
    </ul>
    <!--  -->
    <!--  -->
    <!--  -->
    <div class="tab-content" id="pills-tabContent">
      <div
        class="tab-pane fade show active"
        id="pills-home"
        role="tabpanel"
        aria-labelledby="pills-home-tab">
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
                <td>{defendant.ssn}</td>
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
      </div>
      <!--  -->
      <!--  -->
      <!--  -->
      <div
        class="tab-pane fade"
        id="pills-profile"
        role="tabpanel"
        aria-labelledby="pills-profile-tab">
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
              </tr>
            </thead>
            <tbody id="myTable">
              <tr>
                <td>{defendant.dependant_First}</td>
                <td>{defendant.dependant_Last}</td>
                <td>{defendant.dependant_Middle}</td>
                <td>{defendant.dependant_Dob}</td>
                <td>{defendant.dependant_Ssn}</td>
                <td>{defendant.dependant_Phone}</td>
                <td>{defendant.dependant_State}</td>
                <td>{defendant.dependant_City}</td>
                <td>{defendant.dependant_Address}</td>
                <td>{defendant.dependant_PostalCode}</td>
                <td>{defendant.dependant_AptNum}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
      <!--  -->
      <!--  -->
      <!--  -->
      <div
        class="tab-pane fade"
        id="pills-contact"
        role="tabpanel"
        aria-labelledby="pills-contact-tab">
        <button
          type="button"
          class="btn btn-primary"
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
              </tr>
            </thead>
            <tbody id="myTable">
              {#each defendant.bonds as bonds}
                <tr>
                  <td>{bonds.power_Number}</td>
                  <td>{bonds.status}</td>
                  <td>{bonds.agency}</td>
                  <td>{bonds.agent}</td>
                  <td>{bonds.amount}</td>
                  <td>{bonds.posted_Date}</td>
                  <td>{bonds.forfiture_By}</td>
                </tr>
              {/each}
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
  <div class="DefendantFooter" style="float:right">
    <button type="button" class="btn btn-primary">Edit</button>
    <button type="button" class="btn btn-danger">Delete</button>
  </div>
</div>
