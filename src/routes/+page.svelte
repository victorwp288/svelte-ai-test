<script>
	import {useChat} from "ai/svelte";

	const {messages, handleSubmit, input} = useChat({
		api: "/chat",
	});
</script>


<h1>Ask our ai below</h1>
<ul>
	{#each $messages as message}
		<li>{message.role} says... {message.content}</li>
	{/each}
</ul>

<form on:submit|preventDefault={handleSubmit}>
	<input bind:value={$input} />
	<button>Send</button>
</form>