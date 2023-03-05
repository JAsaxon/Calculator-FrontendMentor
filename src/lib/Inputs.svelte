<script lang="ts">
  export let Change: Function;
  import Input from "./Input.svelte";
</script>

<Input number={7} func={() => Change("NUMBER", "7")} />
<Input number={8} func={() => Change("NUMBER", "8")} />
<Input number={9} func={() => Change("NUMBER", "9")} />
<Input number={"DEL"} func={() => Change("DELETE", 0)} />
<Input number={4} func={() => Change("NUMBER", "4")} />
<Input number={5} func={() => Change("NUMBER", '5')} />
<Input number={6} func={() => Change("NUMBER", '6')} />
<Input number={"+"} func={() => Change("SYMBOL", "+")} />
<Input number={1} func={() => Change("NUMBER", '1')} />
<Input number={2} func={() => Change("NUMBER", '2')} />
<Input number={3} func={() => Change("NUMBER", '3')} />
<Input number={"-"} func={() => Change("SYMBOL", "-")} />
<Input number={"."} func={() => Change("SYMBOL", ".")} />
<Input number={"0"} func={() => Change("NUMBER", '0')} />
<Input number={"/"} func={() => Change("SYMBOL", "/")} />
<Input number={"x"} func={() => Change("SYMBOL", "*")} />
<Input number={"RESET"} func={() => Change("RESET", "")} />
<Input number={"="} func={() => Change("EVALUATE", "=")} />

