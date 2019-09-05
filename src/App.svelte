<script>
  export let name = "";
  export let age = 25;
  export let imageUrl = "https://i.pravatar.cc/125";
  export let userDescription = "";
  export let jobPosition = "";
  import ContactCard from "./ContactCard.svelte";
  import Button from "./Button.svelte";

  // let uppercaseName no es requerido al usar $:
  $: uppercaseName = name.toUpperCase();
  $: console.log(name);

  $: if (name === "juan") {
    age = 31;
    console.log("It runs!");
  }

  function incrementeAge() {
    age += 1;
  }

  function changeName() {
    name = "juan";
  }

  function nameInput(event) {
    const enteredValue = event.target.value;
    name = enteredValue;
  }
</script>

<style>
  h1 {
    color: purple;
  }
</style>

<h1>Hello {uppercaseName}!, my age is {age}</h1>
<button on:click={incrementeAge}>Change Age</button>
<form>
  <input type="text" bind:value={name} placeholder="Full Name" />
  <input type="text" bind:value={jobPosition} placeholder="Job Position" />
  <textarea bind:value={userDescription} placeholder="User Description" />
</form>
<ContactCard userName={name} {userDescription} {imageUrl} {jobPosition} />

<Button>Hey</Button>
<Button variant="primary">Hey</Button>
<Button variant="success">Hey</Button>
