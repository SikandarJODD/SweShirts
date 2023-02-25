<script>
	import '../app.css';
	import { page } from '$app/stores';
	$: RouteId = $page.route.id;
</script>

<div class="navbar bg-base-100 hidden md:flex ">
	<div class="navbar-start ">
		<a class="btn btn-ghost normal-case text-xl hidden md:flex" href="/">Fusion XD</a>
	</div>
	<div class="navbar-center hidden lg:flex">
		<ul class="menu menu-horizontal px-1">
			<li><a href="/" class="mx-1">Home</a></li>
			<li><a href="/products" class="mx-1">Products</a></li>
			<li><a href="/about" class="mx-1">About Us</a></li>
		</ul>
	</div>
</div>
<div class="btm-nav md:hidden">
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
					d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"
				/></svg
			>
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

<div class="px-3 mt-3 md:px-0 md:mt-0">
	<slot />
</div>
