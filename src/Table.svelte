<script>
    //@ts-nocheck
    import {TabulatorFull as Tabulator} from 'tabulator-tables';
    import {onMount} from 'svelte';
  
    
  
    export let data, columns;
  
    let tableComponent;
  
    onMount(() => {
      var table = new Tabulator(tableComponent, {
        data: data, //link data to table
        reactiveData:true, //enable data reactivity
        columns: columns, //define table columns
        
      });
      table.on('rowClick', (e, row) => {
  	alert("Row " + row.getIndex() + " Clicked!!!!");
  })
    });
  </script>
  
  
  <div bind:this={tableComponent}></div>
  
  <svelte:head>
    <link href="https://unpkg.com/tabulator-tables@4.9.1/dist/css/tabulator.min.css" rel="stylesheet">
  </svelte:head>