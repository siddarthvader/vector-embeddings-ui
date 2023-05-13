<script>
	import Header from '$lib/Header.svelte';
</script>

<Header />
<div class="hero h-[calc(100vh-4rem)] bg-base-200">
	<div class="hero-content text-center w-full h-full">
		<div class="w-full h-full flex flex-col">
			<h1 class="text-3xl font-bold my-4">Add Vector Embeddings to your vector database</h1>
			<form class="form-control flex-1 flex flex-col space-y-6">
				<label class=" flex flex-col items-start">
					<span class="font-semibold">Text</span>
					<textarea
						rows="12"
						placeholder="Enter Text to Embed"
						class="textarea rounded-none textarea-primary textarea-lg w-full"
					/>
				</label>
				<div class="flex flex-col items-start">
					<span class="font-semibold">Source</span>
					<input type="text" placeholder="10" class="input input-bordered input-primary w-full" />
					<span class="font-thin"
						>Recommended to add Source URL so that it can be referred by LLM</span
					>
				</div>
				<button class="btn btn-primary self-end">Save</button>
			</form>
		</div>
	</div>
</div>
