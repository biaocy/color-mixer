<script>
  import tinycolor from 'tinycolor2';

  let left = '#000000';
  let right = '#ffffff';
  let result = '#ffffff';

  $: {
    result = tinycolor.mix(tinycolor(left), tinycolor(right), 50).toHexString();
  }


</script>

<div id="container">
  <div id="operand">
    <input type="color" id="left" class="color" bind:value={left} />
    <input type="color" id="right" class="color" bind:value={right} />
  </div>
  <div id="result" class="color" style:background-color={result} />
</div>

<style>
#container {
  display: flex;
  flex-direction: column;
}

#operand {
  display: flex;
}

div.color {
  width: 50px;
  height: 50px;
  border: 1px solid;
  border-color: black;
}

#result {
  width: 100px;
  height: 100px;
}
</style>
