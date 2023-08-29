<script lang="ts">
	import { toastStore } from '@skeletonlabs/skeleton';
	import type { ToastSettings } from '@skeletonlabs/skeleton';
	import { clipboard } from '@skeletonlabs/skeleton';
	import { modalStore } from '@skeletonlabs/skeleton';
	import type { ModalSettings } from '@skeletonlabs/skeleton';
	import { base } from '$app/paths';

	const specialicoUrl = 'https://github.com/KosukeOnishi/sample_specialico';

	const t: ToastSettings = {
		message: 'メールアドレスをコピーしました',
		timeout: 2000
	};

	const modal: ModalSettings = {
		type: 'alert',
		title: 'Example Alert',
		body: 'This is an example modal.',
		image: 'https://i.imgur.com/WOgTG96.gif'
	};

	const apps = [
		{
			title: 'ReadHub',
			path: base + '/readhub.png',
			detail_path: base +'/readhub_detail.png',
			body: '人から本を探せる読書コミュニティアプリです。当初swiftで開発されていたアプリを、flutterを用いてひとりでAndroidに実装しました。'
		},
		{
			title: 'Phily',
			path: base + '/phily.png',
			detail_path: base + '/phily_detail.png',
			body: 'Z世代向け音声通話アプリです。チーム開発で、主にUIや遊び心のあるアニメーションの実装などを担当しました。'
		},
		{
			title: '異才FUTURE',
			path: base + '/isai.png',
			detail_path: base + '/isai_detail.png',
			body: 'WOWWOWの番組『異彩FUTURE うたえミライの歌』の番組内アプリです。Android版アプリを担当しました。'
		},
		{
			title: 'DailyDo',
			path: base + '/dailydo.png',
			detail_path: base + '/dailydo_detail.png',
			body: '日単位でタスク管理する、というコンセプトのToDoアプリです。個人開発でつくり、Google Play Storeでリリースしました。SNSへのシェア機能や、多言語対応などを実装しました。'
		}
	];

	function onTapEmail() {
		toastStore.trigger(t);
	}

	function onTapApp(app: { title: string; path: string; detail_path: string; body: string }) {
		modalStore.trigger({
			type: 'alert',
			title: app.title,
			body: app.body,
			image: app.detail_path
		});
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
				src="{base}/cup.svg"
				alt="a coffee cup with flutter logo inside"
				class="-translate-y-8 translate-x-2 sm:translate-x-0 pb-4 sm:pb-0"
			/>
		</div>
	</div>
</div>

<div class="mx-auto mt-40 px-6">
	<div class="flex flex-col items-center">
		<p class="inline-block text-3xl font-semibold pb-20">最近のプロジェクト</p>
		<div
			class="group flex flex-col lg:flex-row max-w-6xl justify-between items-center lg:items-start"
		>
			<a href={specialicoUrl} target="_blank" rel="noopener noreferrer">
				<div class="mr-0 lg:mr-10 xl:w-[524px] xl:max-w-[524px] max-w-[450px] relative">
					<img
						src="{base}/specialico.png"
						alt="feature graphic of the app called specialico"
						class="rounded-lg object-contain"
					/>
					<div
						class="absolute top-0 opacity-0 bg-white h-full w-full rounded-lg group-hover:opacity-30"
					/>
				</div>
			</a>
			<div
				class="ml-0 lg:ml-10 flex flex-col items-center lg:items-start xl:w-[524px] lg:w-[450px] translate-y-0 lg:-translate-y-1"
			>
				<a href={specialicoUrl} target="_blank" rel="noopener noreferrer">
					<p class="font-semibold text-2xl mt-10 lg:mt-0 group-hover:opacity-75">Specialico</p>
				</a>
				<a href={specialicoUrl} target="_blank" rel="noopener noreferrer">
					<p
						class="tracking-wide leading-8 mt-4 text-center lg:text-start px-0 md:px-10 lg:px-0 group-hover:opacity-75"
					/></a
				>
				<a href={specialicoUrl} target="_blank" rel="noopener noreferrer">
					<p class="group-hover:opacity-75 text-center lg:text-start">
						スペシャルティコーヒーが飲めるコーヒーショップを探せるアプリ。Flutter、Firebase、Google
						Admob、Maps SDKなどを使用。
					</p>
				</a>
				<a href={specialicoUrl} target="_blank" rel="noopener noreferrer">
					<p class="text-gray-500 text-sm group-hover:opacity-75">→詳しく見る</p>
				</a>
				<div class="flex lg:mt-4 mt-8 group/buttons">
					<a
						href="https://apps.apple.com/jp/app/specialico/id6462790050"
						target="_blank"
						rel="noopener noreferrer"
						><img src="{base}/app_store.svg" alt="app store button" class="object-contain h-11" />
					</a>
					<a
						href="https://play.google.com/store/apps/details?id=com.specialico"
						target="_blank"
						rel="noopener noreferrer"
						class="ml-4"
						><img src="{base}/play_store.png" alt="app store button" class="object-contain h-11" />
					</a>
				</div>
			</div>
		</div>
	</div>
</div>

<div class="w-fit mx-auto mt-40 px-6">
	<div class="flex flex-col items-center">
		<p class="w-fit text-3xl font-semibold">過去のプロジェクト</p>
		<p class="pt-10 pb-16 text-gray-500 tracking-wide max-w-4xl text-center">
			以下のプロジェクトは、すべてFlutter製で実際にリリースされたものです。
		</p>
		<div class="flex flex-wrap justify-center">
			{#each apps as app}
				<button on:click={() => onTapApp(app)} class="w-1/2 md:w-auto">
					<div class="flex flex-col items-center pb-8 md:pb-0 group">
						<div class="w-[120px] h-[120px] mx-0 2xl:mx-[106px] xl:mx-[90px] lg:mx-[58px] md:mx-7">
							<img
								src='{app.path}'
								alt="app icon of the app called {app.title}"
								class="rounded-3xl object-contain group-hover:opacity-75"
							/>
						</div>
						<p class="pt-4 text-xl font-semibold group-hover:opacity-75">{app.title}</p>
					</div>
				</button>
			{/each}
		</div>
	</div>
</div>

<div class="w-fit mx-auto mt-32 md:mt-40 mb-40 px-6 sm:px-12">
	<div class="flex flex-col items-center">
		<p class="inline-block text-3xl font-semibold">About Me</p>
		<p class="pt-10 text-gray-500 text-center leading-8 tracking-wide max-w-4xl">
			SFC在学中に、先輩の起業したスタートアップに誘われてFlutter開発をスタート。2つのアプリのリリース、サービスの指標設計・管理に携わりました。その会社を辞めたのち、いくつかのアプリを個人で開発しました。
		</p>
		<p class="pt-3 text-gray-500 text-center leading-8 tracking-wide max-w-4xl">
			Flutter以外では、TypeScript、SQL、Pythonなどを扱えます。大学の研究としてPythonを用いてちょっとしたシステムの実装をしました。また、Webのフロントエンドを勉強中です。（このサイトは、SvelteKitとtailwindで実装されています。）
		</p>
		<div class="flex pt-3 text-gray-500 text-center leading-8 tracking-wide max-w-4xl">
			<div>Contact:</div>
			<button use:clipboard={'kosuke.nsh@gmail.com'} class="ml-2 underline" on:click={onTapEmail}
				>kosuke.nsh@gmail.com</button
			>
		</div>
	</div>
</div>
