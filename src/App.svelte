<script lang="ts">
  // この値をinputで書き換えるのでletを使わなければいけないの微妙
	let text = "Svelte";
  // const handleChange = (e) => {
  //   text = e.target.value
  // }

  let count = 0;
  const handleClick = () => count++

  let isActive = false;
  const toggle = () => isActive = !isActive
</script>

<main>
	<h1>Hello {text}!</h1>
  <!-- svelteではこっちの方がレスコードで推奨 -->
  <input type=text bind:value={text}>
  <!-- <input type=text on:input={handleChange}> -->

  <input type=number bind:value={count}>
  <button on:click={handleClick}>+</button>

  <button class:active={isActive} on:click={toggle}>いいね</button>
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

  .active {
    background-color: #ff3e00;
    color: white;
  }
</style>