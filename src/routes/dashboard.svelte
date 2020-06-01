<script>
  let balance = "$10,000";
  import { onMount } from "svelte";

  function createChart() {
    var ctx = document.getElementById("myChart").getContext("2d");
    var chart = new Chart(ctx, {
      // The type of chart we want to create
      type: "line",

      // The data for our dataset
      data: {
        labels: [
          "January",
          "February",
          "March",
          "April",
          "May",
          "June",
          "July"
        ],
        datasets: [
          {
            label: "My First dataset",
            backgroundColor: "rgb(255, 99, 132)",
            borderColor: "rgb(255, 99, 132)",
            data: [0, 10, 5, 2, 20, 30, 45]
          }
        ]
      },

      // Configuration options go here
      options: {}
    });
  }

  onMount(createChart);
</script>

<style>
  .container {
    width: 100%;
    margin: auto;
    background-color: lightskyblue;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
  }
</style>

<h4>Dashboard</h4>

<div class="container">
  <div class="left" style="flex: 1;">
    <div class="card text-center" style="width: 18rem;">
      <div class="card-body">
        <h4 class="card-title">Total Balance</h4>
        <h5 class="card-text">
          <button type="button" class="btn btn-success">
            <h4>{balance}</h4>
          </button>
        </h5>
      </div>
    </div>
  </div>
  <div class="right">
    <canvas id="myChart" style="flex: 2;" />
  </div>
</div>
