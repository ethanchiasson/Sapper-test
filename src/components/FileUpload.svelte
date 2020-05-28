<script>
  export let multiple = true;
  let files = [];
  function handleChange(e) {
    files = Array.from(e.target.files);
  }
</script>

<h4>Upload a File</h4>
<input
  type="file"
  style="margin-top: 5px"
  {multiple}
  on:change={handleChange} />
<div class="table table-responsive" style="margin-top: 5px">
  <table class="table table-striped table-dark">
    <thead>
      <tr>
        <th scope="col">File Name</th>
        <th scope="col">Size</th>
        <th scope="col">Type</th>
        <th scope="col">Upload Date</th>
      </tr>
    </thead>
    <tbody id="myTable">
      {#each files as f, i (i)}
        <tr>
          <td>{f.name}</td>
          <td>{f.size}</td>
          <td>{f.type}</td>
          <td>{new Date(f.lastModified)}</td>
          <td>
            <button type="button" class="btn btn-danger">Delete</button>
          </td>
        </tr>
      {/each}
    </tbody>
  </table>
</div>
