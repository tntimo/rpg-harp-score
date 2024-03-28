<script>
	export let name;
  let data = localStorage.getItem('myData') || '';

  function handleInput(event) {
    data = event.target.value;
    localStorage.setItem('myData', data);
  }
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<div>
		<h1>Simple SPA with Svelte</h1>
		<textarea bind:value={data} on:input={handleInput} placeholder="Enter data..."></textarea>
		<p>{data}</p>
	</div>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>

