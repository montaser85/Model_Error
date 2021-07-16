<script>
    import * as jsonData from '../Stores/Data.json';
    import App from "../App.svelte";

    console.log(jsonData); 
</script>

<div>
    <div class="poll-list">
        {#each jsonData.Models as item (item.id)}
          <div>
            <h3>Model: {item.id}</h3>
            <ul>{item.ModelName}</ul>
            <ul>{item.PerformanceMetric}</ul>
            <ul>{item.value}</ul>  
          </div>
        {/each}
      </div>
</div>


<!-- how to read json file: https://stackoverflow.com/questions/60779816/how-to-access-local-json-file-via-svelte -->