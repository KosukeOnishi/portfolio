<div class="h-screen w-full bg-primary-500 flex items-center">
	<div class="w-full flex items-center">
		<div class="w-48 text-center mx-auto">
			<p>left</p>
		</div>
		<div class="w-48 text-center mx-auto">
			<p>right</p>
		</div>
	</div>
</div>

{#each Array(40) as _, index}
	<p>mid contents {index}</p>
{/each}
