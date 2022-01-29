<script>
  import ContactCard from './ContactCard.svelte';

  let name = 'Max';
  let title = '';
  let imageUrl = '';
  let description = '';
  let age = 30;

  $: upperCaseName = name.toUpperCase();

  function incrementAge() {
    age += 1;
  }

  function changeName() {
    name = 'Maximiliam';
  }

  function nameInput(event) {
    const enteredValue = event.target.value;
    name = enteredValue;
  }
</script>

<h1>Hello {upperCaseName}, my age is {age}!</h1>
<button on:click={incrementAge}>Change Age</button>
<button on:click={changeName}>Change Name</button>
<!-- <input type="text" value="{name}" on:input="{nameInput}"> -->
<input type="text" bind:value={name} />
<input type="text" bind:value={title} />
<input type="text" bind:value={imageUrl} />
<input type="text" bind:value={description} />

<ContactCard userName={name} jobTitle={title} {description} userImg={imageUrl} />

<style>
  h1 {
    color: purple;
  }
</style>
