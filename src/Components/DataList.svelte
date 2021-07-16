<script>
    import * as jsonData from '../Stores/Data.json';
    import App from "../App.svelte";

    console.log(jsonData); 
</script>

<div>
    <div class="poll-list">
        {#each jsonData.predictions as item (item.image_id)}
          <div>
            <h3>ImageID: {item.image_id}</h3>
            <ul>Image_Attribute: {item.attributes}</ul>
            <ul>FileName: {item.image_filename}</ul>
            <ul>
              {#each item.true_boxes as box (box.box_id)}
              <ul>BoxID: {box.box_id}</ul>
              <ul>BoxLabel: {box.label}</ul>
              {/each}
            </ul>  
          </div>
        {/each}
      </div>
</div>


<!-- how to read json file: https://stackoverflow.com/questions/60779816/how-to-access-local-json-file-via-svelte -->