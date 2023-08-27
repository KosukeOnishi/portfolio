<script lang="ts">
	import '../theme.postcss';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	import { AppShell } from '@skeletonlabs/skeleton';
	import { Toast } from '@skeletonlabs/skeleton';
	import { Modal } from '@skeletonlabs/skeleton';
</script>

<Modal buttonTextCancel="閉じる" flyY={0} padding='p-8'/>
<Toast />

<AppShell>
	<!-- (header) -->
	<slot />
	<svelte:fragment slot="pageFooter">
		<div class="bg-white py-6 px-16 w-full flex justify-between">
			<span>© Kosuke Onishi</span>
			<div class="flex">
				<a href="https://github.com/KosukeOnishi" target="_blank" rel="noopener noreferrer"
					>GitHub</a
				>
				<a
					href="https://www.facebook.com/ksk.onsh"
					class="ml-8"
					target="_blank"
					rel="noopener noreferrer">Facebook</a
				>
			</div>
		</div>
	</svelte:fragment>
</AppShell>
