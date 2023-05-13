<script>
	import Header from '$lib/components/Header.svelte';
	import { embed_source, embed_text } from '$lib/store';

	function embedSubmit() {
		console.log($embed_text);
		console.log($embed_source);
	}

	function embedTextChange(e) {
		embed_text.set(e.target.value);
	}

	function embedSourceChange(e) {
		embed_source.set(e.target.value);
	}
</script>

<Header />
<div class="hero h-[calc(100vh-4rem)] bg-base-200">
	<div class="hero-content text-center w-full h-full">
		<div class="w-full h-full flex flex-col">
			<h1 class="text-3xl font-bold my-4">Add Vector Embeddings to your vector database</h1>
			<form
				on:submit|preventDefault={embedSubmit}
				class="form-control flex-1 flex flex-col space-y-6"
			>
				<label class=" flex flex-col items-start">
					<span class="font-semibold">Text</span>
					<textarea
						rows="12"
						placeholder="Enter Text to Embed"
						class="textarea rounded-none textarea-primary textarea-lg w-full"
						on:input={embedTextChange}
					/>
				</label>
				<div class="flex flex-col items-start">
					<span class="font-semibold">Source</span>
					<input
						type="text"
						placeholder="https://www.source.com/"
						class="input input-bordered input-primary w-full"
						on:input={embedSourceChange}
					/>
					<span class="font-thin"
						>Recommended to add Source URL so that it can be referred by LLM</span
					>
				</div>
				<button class="btn btn-primary self-end">Save</button>
			</form>
		</div>
	</div>
</div>
