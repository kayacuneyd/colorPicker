<script>
  import { HsvPicker } from "svelte-color-picker";

  function colorCallback(rgb) {
    let r = rgb.detail.r;
    let g = rgb.detail.g;
    let b = rgb.detail.b;
    let bw = 255 - (r + g + b) / 4;
    let main = document.querySelector(".main");
    main.style.background = `rgb(${r},${g},${b})`;
    let header = document.querySelector("h3");
    header.style.color = `rgb(${bw},${bw},${bw})`;
    let p = document.querySelector("p");
    p.style.color = `rgb(${bw},${bw},${bw})`;
    let body = document.querySelector("body");
    body.style.background = `rgb(${bw},${bw},${bw})`;
  }
</script>

<div class="main">
  <div class="container">
    <h1>Color Picker</h1>
    <HsvPicker on:colorChange={colorCallback} startColor={"#82EAEA"} />
  </div>
</div>

<style>
  .main {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }

  .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex-grow: 1;
  }
</style>
