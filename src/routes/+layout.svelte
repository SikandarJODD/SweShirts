<script>
	import '../app.css';
	import { page } from '$app/stores';
	$: RouteId = $page.route.id;
	import AOS from 'aos';
	import 'aos/dist/aos.css';
	import { onMount } from 'svelte';
	import LogoImg from '$lib/jacket.png';
	onMount(() => {
		AOS.init();
	});
</script>

<div class="navbar bg-base-100 hidden md:flex px-20  border-b-2 border-slate-300">
	<div class="navbar-start ">
		<img src="https://cdn-icons-png.flaticon.com/512/7394/7394940.png" alt="Logo" width="40" />
		<a
			class="btn btn-ghost normal-case text-3xl hidden md:flex mx-2 font-bold text-cyan-500 "
			href="/">Fusion XD</a
		>
	</div>
	<div class="navbar-center hidden lg:flex ">
		<ul class="menu menu-horizontal px-1">
			<li><a href="/" class="mx-1">Home</a></li>
			<li><a href="/products" class="mx-1">Products</a></li>
			<li><a href="/upload" class="mx-1">Upload</a></li>
			<li><a href="/about" class="mx-1">About Us</a></li>
		</ul>
	</div>
</div>
<div class="btm-nav md:hidden z-10">
	<a href="/" class={RouteId == '/' ? 'active text-info' : ' '}>
		<button>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-5 w-5"
				fill="none"
				viewBox="0 0 24 24"
				stroke="currentColor"
				><path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"
				/></svg
			>
		</button>
	</a>
	<a href="/products" class={RouteId == '/products' ? 'active text-info' : ' '}>
		<button>
			<!-- <svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-5 w-5"
				fill="none"
				viewBox="0 0 24 24"
				stroke="currentColor"
				><path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"
				/></svg
			> -->
			<img src={LogoImg} alt="" width="30" />
		</button>
	</a>
	<a href="/about" class={RouteId == '/about' ? 'active text-info' : ' '}>
		<button>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-5 w-5"
				fill="none"
				viewBox="0 0 24 24"
				stroke="currentColor"
				><path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
				/></svg
			>
		</button>
	</a>
</div>

<div class="mt-3 md:px-0 md:mt-0">
	<slot />
</div>
<footer
	class="footer items-center p-4 bg-neutral text-neutral-content flex justify-center "
>
	<div class="items-center grid-flow-col md:px-32  mb-16 md:mb-0 ">
		<img src="https://cdn-icons-png.flaticon.com/512/7394/7394940.png" alt="" width="40" />
		<p class="text-sm md:text-lg">Copyright © 2023 - All right reserved</p>
	</div>
	<!-- <div class="grid-flow-col gap-4 md:place-self-center md:justify-self-end px-32 hidden md:grid">
		<a
			><svg
				xmlns="http://www.w3.org/2000/svg"
				width="24"
				height="24"
				viewBox="0 0 24 24"
				class="fill-current"
				><path
					d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"
				/></svg
			>
		</a>
		<a
			><svg
				xmlns="http://www.w3.org/2000/svg"
				width="24"
				height="24"
				viewBox="0 0 24 24"
				class="fill-current"
				><path
					d="M19.615 3.184c-3.604-.246-11.631-.245-15.23 0-3.897.266-4.356 2.62-4.385 8.816.029 6.185.484 8.549 4.385 8.816 3.6.245 11.626.246 15.23 0 3.897-.266 4.356-2.62 4.385-8.816-.029-6.185-.484-8.549-4.385-8.816zm-10.615 12.816v-8l8 3.993-8 4.007z"
				/></svg
			></a
		>
		<a
			><svg
				xmlns="http://www.w3.org/2000/svg"
				width="24"
				height="24"
				viewBox="0 0 24 24"
				class="fill-current"
				><path
					d="M9 8h-3v4h3v12h5v-12h3.642l.358-4h-4v-1.667c0-.955.192-1.333 1.115-1.333h2.885v-5h-3.808c-3.596 0-5.192 1.583-5.192 4.615v3.385z"
				/></svg
			></a
		>
	</div> -->
</footer>

<style>
	[data-aos] {
		visibility: hidden;
	}
	[data-aos].animated {
		visibility: visible;
	}
</style>
