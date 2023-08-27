<script lang="ts">
	import { Toast, toastStore } from '@skeletonlabs/skeleton';
	import type { ToastSettings } from '@skeletonlabs/skeleton';
	import { clipboard } from '@skeletonlabs/skeleton';

	const t: ToastSettings = {
		message: 'メールアドレスをコピーしました',
		timeout: 2000
	};

	const apps = [
		{
			title: 'ReadHub',
			path: '/readhub.png'
		},
		{
			title: 'Phily',
			path: '/phily.png'
		},
		{
			title: 'isai',
			path: '/isai.png'
		},
		{
			title: 'DailyDo',
			path: '/dailydo.png'
		}
	];

	function onTapEmail() {
		toastStore.trigger(t);
	}
</script>

<div class="h-screen w-full bg-primary-500 flex items-center bg-[url('/noise.svg')]">
	<div class="w-full flex flex-col-reverse sm:flex-row items-center">
		<div class="w-fit text-center mx-auto text-white selection:bg-secondary-500">
			<p class="font-medium text-4xl tracking-wide -translate-x-3">Kosuke Onishi</p>
			<p class="pt-6 text-xl w-fit leading-8 tracking-widest font-light">+22 years old</p>
			<p class="text-xl w-fit leading-8 tracking-widest font-light">Flutter Developer +1 year</p>
			<p class="text-xl w-fit leading-8 tracking-widest font-light -translate-x-[0.13rem]">
				コーヒーフリーク +8 years
			</p>
		</div>
		<div class="mx-auto">
			<img
				src="/cup.svg"
				alt="a coffee cup with flutter logo inside"
				class="-translate-y-8 pb-4 sm:pb-0"
			/>
		</div>
	</div>
</div>

<div class="mx-auto mt-40 px-6">
	<div class="flex flex-col items-center">
		<p class="inline-block text-3xl font-bold pb-20">最近のプロジェクト</p>
		<div class="flex flex-col lg:flex-row max-w-6xl justify-between items-center lg:items-start">
			<div class="mr-0 lg:mr-10 xl:w-[524px] xl:max-w-[524px] max-w-[450px]">
				<img
					src="/specialico.png"
					alt="feature graphic of the app called specialico"
					class="rounded-lg object-contain"
				/>
			</div>
			<div
				class="ml-0 lg:ml-10 flex flex-col items-center lg:items-start xl:w-[524px] lg:w-[450px] translate-y-0 lg:-translate-y-1"
			>
				<p class="font-bold text-2xl mt-10 lg:mt-0">Specialico</p>
				<p class="tracking-wide leading-8 mt-4 text-center lg:text-start px-0 md:px-10 lg:px-0">
					スペシャルティコーヒーが飲めるコーヒーショップを探せるアプリ。Flutter、Firebase、Google
					Admob、Maps SDKなどを使用。
				</p>
				<p class="text-gray-500 text-sm">→詳しく見る</p>
				<div class="flex lg:mt-4 mt-8">
					<a
						href="https://apps.apple.com/jp/app/specialico/id6462790050"
						target="_blank"
						rel="noopener noreferrer"
						><img src="/app_store.svg" alt="app store button" class="object-contain h-11" />
					</a>
					<a
						href="https://play.google.com/store/apps/details?id=com.specialico"
						target="_blank"
						rel="noopener noreferrer"
						class="ml-4"
						><img src="/play_store.png" alt="app store button" class="object-contain h-11" />
					</a>
				</div>
			</div>
		</div>
	</div>
</div>

<div class="w-fit mx-auto mt-40 px-6">
	<div class="flex flex-col items-center">
		<p class="w-fit text-3xl font-bold">過去のプロジェクト</p>
		<p class="pt-10 pb-16 text-gray-500 tracking-wide max-w-4xl">
			以下のプロジェクトは、すべてFlutter製で実際にリリースされたものです。
		</p>
		<div class="flex flex-wrap justify-center">
			{#each apps as app}
				<div class="flex flex-col items-center w-1/2 md:w-auto pb-8 md:pb-0">
					<div class="w-[120px] h-[120px] mx-0 2xl:mx-[106px] xl:mx-[90px] lg:mx-[58px] md:mx-7">
						<img
							src={app.path}
							alt="app icon of the app called {app.title}"
							class="rounded-3xl object-contain"
						/>
					</div>
					<p class="pt-4 text-xl font-bold">{app.title}</p>
				</div>
			{/each}
		</div>
	</div>
</div>

<div class="w-fit mx-auto mt-32 md:mt-40 mb-40 px-6 sm:px-12">
	<div class="flex flex-col items-center">
		<p class="inline-block text-3xl font-bold">About Me</p>
		<p class="pt-10 text-gray-500 text-center leading-8 tracking-wide max-w-4xl">
			SFC在学中に、先輩の起業したスタートアップに誘われてFlutter開発をスタート。2つのアプリのリリース、サービスの指標設計・管理に携わりました。その会社を辞めたのち、いくつかのアプリを個人で開発しました。
		</p>
		<p class="pt-3 text-gray-500 text-center leading-8 tracking-wide max-w-4xl">
			Flutter以外では、TypeScript、SQL、Pythonなどを扱えます。大学の研究としてPythonを用いてちょっとしたシステムの実装をしました。また、Webのフロントエンドを勉強中です。（このサイトは、SvelteKitとtailwindで実装されています。）
		</p>
		<div class="flex pt-3 text-gray-500 text-center leading-8 tracking-wide max-w-4xl">
			<div>Contact:</div>
			<button use:clipboard={'kosuke.nsh@gmail.com'} class="ml-2 underline" on:click={onTapEmail}>kosuke.nsh@gmail.com</button>
		</div>
	</div>
</div>
