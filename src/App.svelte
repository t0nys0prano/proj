<script>
	import Test from './Test.svelte';
	let name = "John";
	let age = 5;
	let counter = 0;
	$: dogYears = age * 7;
	function add() {
		age += 1;
	}
	function sub() {
		age -= 1;
	}
	function bing(){
		if (counter>0) {
			counter -= 1;
		}
		else counter += 1;
	}	
</script>

<style>
	h1{
		color: red; 
		text-align: left
	}
	h2{
		color: blue; 
		text-align: center
	}
	.start{
        background-color: skyblue;
        border-color: springgreen;
        width: 300px;
        border-width: 5px;
    }
</style>

<h1>Hello {name}, you are {age}!</h1>
<h2>You are {dogYears} in dog years.
<br><button on:click={add}>+</button>
<button on:click={sub}>-</button></h2>
<br><button class="start" on:click={bing}>ding dong</button>
{#if counter > 0}
	<Test />
{/if}
