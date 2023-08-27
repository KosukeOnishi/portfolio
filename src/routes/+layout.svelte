<script lang="ts">
	import '../theme.postcss';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	import { AppShell } from '@skeletonlabs/skeleton';
</script>

<AppShell>
	<!-- (header) -->
	<slot />
	<svelte:fragment slot="pageFooter"><div class="bg-white py-6 px-16">Footer</div></svelte:fragment>
</AppShell>
