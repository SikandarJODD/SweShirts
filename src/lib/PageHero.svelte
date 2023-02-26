<script>
	import MainImg from './mainImg.png';
</script>

<section class="text-gray-600 body-font">
	<div class="container mx-auto flex px-5 py-3 md:py-10 md:flex-row flex-col items-center">
		<div
			class="lg:flex-grow md:w-1/2 lg:pr-24 md:pr-16 flex flex-col md:items-start md:text-left mb-16 md:mb-0 items-center text-center"
		>
			<h1 class="title-font font-bold sm:text-6xl text-5xl mb-4  text-slate-200">
				Fusion XD <span class="text-sky-400">SweatShirts</span>
				<br class="hidden lg:inline-block" />
			</h1>
			<div class="mb-8 leading-relaxed hidden md:flex flex-col ">
				<h2 class="text-xl my-1">
					<span class="badge badge-lg p-4 hover:bg-slate-700">High Quality </span>
				</h2>
				<h2 class="text-xl my-1">
					<span class="badge badge-lg p-4 hover:bg-slate-700">Machine Wash</span>
				</h2>
				<div class="flex">
					<h2 class="text-xl m-1">
						<span class="badge badge-lg p-4 badge-primary hover:bg-blue-600 hover:text-white"
							>Hoodies</span
						>
					</h2>
					<h2 class="text-xl m-1">
						<span class="badge badge-lg p-4 badge-primary hover:bg-blue-600 hover:text-white"
							>Puff Print</span
						>
					</h2>
					<h2 class="text-xl m-1">
						<span class="badge badge-lg p-4 badge-primary hover:bg-blue-600 hover:text-white"
							>Relaxed fit</span
						>
					</h2>
				</div>
				<h2 class="text-xl my-1">
					<span class="badge badge-lg p-4 hover:bg-slate-700">Ribbed Cuffs & Hem</span>
				</h2>
			</div>
			<div class="flex justify-center">
				<button
					class="inline-flex text-white bg-indigo-500 border-0 py-2 px-6 focus:outline-none hover:bg-indigo-600 rounded text-lg"
					>Buy Now</button
				>
				<button
					class="ml-4 inline-flex text-gray-700 bg-gray-100 border-0 py-2 px-6 focus:outline-none hover:bg-gray-200 rounded text-lg"
					>Products</button
				>
			</div>
		</div>
		<div class="lg:max-w-lg lg:w-full md:w-1/2 w-5/6 drop-shadow-2xl">
			<img
				class="object-cover object-center rounded-xl w-[400px] drop-shadow-2xl"
				alt="hero"
				src={MainImg}
			/>
		</div>
	</div>
</section>
