<script lang="ts">
  import svelteLogo from "./assets/svelte.svg";
  import Counter from "./lib/Counter.svelte";
  import Inputs from "./lib/Inputs.svelte";
  import { evaluate } from "mathjs";
  let num = "0";
  let style = 0
  $:  calcStyle = `${style * 3.3 + 0.25}em`
  $: console.log(calcStyle)
  const regex = new RegExp("[-,+,x,\/,*,=,.]$");
  function Store(dispatch, val) {
    switch (dispatch) {
      case "NUMBER":
        if (num === "0") {
          num = val;
        } else {
          num += val;
        }

        break;
      case "SYMBOL":
        console.log(num);
        if (num !== "0") {
          if (!num.match(regex,)) {
            num += val;
          } else {
            num = num.slice(0, -1);
            num += val;


          }
        }
        break;
      case "DELETE":
        num = num.slice(0, -1);
        if (num === "") {
          num = "0";
        }
        break;
      case "RESET":
        num = "0";
        break;
      case "EVALUATE":
        num = evaluate(num).toString().slice(0,10);
    }
  }
</script>

<div class="calculator theme{style+1}">
  <div class="themeSwitcherContainer">
    <form action="">
      <div class="name">THEME</div>
      <span class="changer" style="left:{calcStyle}"></span>
      <div class="label">1</div>
      <input type="radio" name="theme" id="" on:click={()=> style=0}>
      <div class="label">2</div>
      
      <input type="radio" name="theme" id="" on:click={()=> style=1}>
      <div class="label">3</div>
      
      <input type="radio" name="theme" id="" on:click={()=> style=2}>
      
    </form>
    <h1>calculator</h1>
  </div>
  <div class="screen "><div class="innerScreen">{num}</div></div>
  <div class="inputs">
    <Inputs Change={Store} />
  </div>
</div>
