<script>
  import FileUpload from "../components/FileUpload.svelte";
  import Payments from "../components/Payments.svelte";
  import Bond from "../components/BondsTab.svelte";
  import Defendant from "../components/DefendantTab.svelte";
  import Dependant from "../components/DependantTab.svelte";

  let agents = {
    names: [
      {
        agent_name: "Jon"
      },
      {
        agent_name: "Mike"
      }
    ]
  };

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
    ],
    payments: [
      {
        amount: "1560.89",
        cashier: "John Smith",
        date: new Date(),
        payment_type: "PayPal"
      },
      {
        amount: "50475.5",
        cashier: "Jane Jones",
        date: new Date(),
        payment_type: "Cash"
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

  .defendantHeader > .left > span {
    padding: 6px;
    font-size: 0.9em;
  }

  .breadcrumb {
    background-color: #212b38;
  }
</style>

<svelte:head>
  <title>Defendant - {defendant.name}</title>
</svelte:head>
<div class="container">
  <nav aria-label="breadcrumb">
    <ol class="breadcrumb">
      <li class="breadcrumb-item">
        <a href="/">Defendants</a>
      </li>
      <li class="breadcrumb-item active" aria-current="page">
        {defendant.first} {defendant.middle} {defendant.last}
      </li>
    </ol>
  </nav>
  <div class="defendantHeader" style="display:flex">
    <div class="left" style="flex:2">
      <h3>{defendant.first} {defendant.middle} {defendant.last}</h3>
      <span class="badge badge-pill badge-danger">{defendant.status}</span>
    </div>
    <div class="right" style="flex:1">
      <h3 style="float: right;">
        <span class="badge badge-dark">${defendant.balance}</span>
      </h3>
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
          Dependants
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
      <li class="nav-item" role="presentation">
        <a
          class="nav-link"
          id="pills"
          data-toggle="pill"
          href="#pills-contact3"
          role="tab"
          aria-controls="pills-contact"
          aria-selected="false">
          Payments
        </a>
      </li>
      <li class="nav-item" role="presentation">
        <a
          class="nav-link"
          id="pills"
          data-toggle="pill"
          href="#pills-contact2"
          role="tab"
          aria-controls="pills-contact"
          aria-selected="false">
          Documents
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
        <Defendant {defendant} />
      </div>
      <!--  -->
      <!--  -->
      <!--  -->
      <div
        class="tab-pane fade"
        id="pills-profile"
        role="tabpanel"
        aria-labelledby="pills-profile-tab">
        <Dependant {defendant} name={defendant.first + ' ' + defendant.last} />
      </div>
      <!--  -->
      <!--  -->
      <!--  -->
      <div
        class="tab-pane fade"
        id="pills-contact"
        role="tabpanel"
        aria-labelledby="pills-contact-tab">
        <Bond
          name={defendant.first + ' ' + defendant.last}
          {defendant}
          {agents} />
      </div>
      <div
        class="tab-pane fade"
        id="pills-contact2"
        role="tabpanel"
        aria-labelledby="pills-contact-tab2">
        <div class="defendantFileUpload">
          <div class="fileUpload">
            <FileUpload />
          </div>
        </div>
      </div>
      <div
        class="tab-pane fade"
        id="pills-contact3"
        role="tabpanel"
        aria-labelledby="pills-contact-tab3">
        <div class="defendantFileUpload">
          <div class="payments">
            <Payments
              name={defendant.first + ' ' + defendant.last}
              {defendant}
              {agents} />
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
