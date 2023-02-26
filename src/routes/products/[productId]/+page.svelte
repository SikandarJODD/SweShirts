<script>
	import { page } from '$app/stores';
	$: RouteId = $page.params.productId;
	$: overAll = RouteId + 1;
	$: console.log(RouteId);

	import Img1 from '$lib/img1.jpg';
	import Img2 from '$lib/img2.jpg';
	import Img3 from '$lib/img3.jpg';
	import Img4 from '$lib/img4.jpg';
	import Img5 from '$lib/img5.jpg';
	import Img6 from '$lib/img6.jpg';
	import Img7 from '$lib/img7.jpg';
	import Img8 from '$lib/img8.jpg';
	import Img9 from '$lib/images/img1.jpg';
	import Img10 from '$lib/images/img2.jpg';
	import Img11 from '$lib/images/img3.jpg';
	import Img12 from '$lib/images/img4.jpg';
	import Img13 from '$lib/images/img5.jpg';
	import Img14 from '$lib/images/img6.jpg';
	import Img15 from '$lib/images/img7.jpg';
	import Img16 from '$lib/images/img8.jpg';
	let data = [
		{
			id: 1,
			title: 'Drippy Drill',
			imgSrc: Img1,
			price: 1500
		},
		{
			id: 2,
			title: 'Fusion Cofii',
			imgSrc: Img2,
			price: 1500
		},
		{
			id: 3,
			title: 'Fusion Spark',
			imgSrc: Img3,
			price: 1500
		},
		{
			id: 4,
			title: 'Fuzzy Lofi',
			imgSrc: Img4,
			price: 1500
		},
		{
			id: 5,
			title: 'Classic Fuzzy',
			imgSrc: Img5,
			price: 1500
		},
		{
			id: 6,
			title: 'Thik Art',
			imgSrc: Img6,
			price: 1500
		},
		{
			id: 7,
			title: 'Clean Flean',
			imgSrc: Img7,
			price: 1500
		},
		{
			id: 8,
			title: 'Japanese Hoddie',
			imgSrc: Img8,
			price: 1500
		},
		{
			id: 9,
			title: 'Sunny Cool',
			imgSrc: Img9,
			price: 1500
		},
		{
			id: 10,
			title: 'Uchia Legacy',
			imgSrc: Img10,
			price: 1500
		},
		{
			id: 11,
			title: 'Pupmkin Fuffy',
			imgSrc: Img11,
			price: 1500
		},
		{
			id: 12,
			title: 'Loner Wolf',
			imgSrc: Img12,
			price: 1500
		},
		{
			id: 13,
			title: 'Peace Hills',
			imgSrc: Img13,
			price: 1500
		},
		{
			id: 14,
			title: 'Anime Pop',
			imgSrc: Img14,
			price: 1500
		},
		{
			id: 15,
			title: 'Anyna Cuffy',
			imgSrc: Img15,
			price: 1500
		},
		{
			id: 16,
			title: 'Goku Blast',
			imgSrc: Img16,
			price: 1500
		}
	];
</script>

<div class=" py-6 sm:py-8 lg:py-12 mb-20">
	<div class="max-w-screen-xl px-4 md:px-8 mx-auto">
		<div class="grid md:grid-cols-2 gap-8">
			<!-- images - start -->
			<div class="grid lg:grid-cols-5 gap-4">
				<div class="lg:col-span-4 bg-gray-100 rounded-lg overflow-hidden relative">
					<!-- svelte-ignore a11y-img-redundant-alt -->
					<img
						src={data[RouteId - 1].imgSrc}
						loading="lazy"
						alt="Photo by Himanshu Dewangan"
						class="w-full h-full object-cover object-center"
					/>

					<span
						class="bg-red-500 text-white text-sm tracking-wider uppercase rounded-br-lg absolute left-0 top-0 px-3 py-1.5"
						>sale</span
					>
				</div>
			</div>
			<!-- images - end -->

			<!-- content - start -->
			<div class="md:py-8">
				<!-- name - start -->
				<div class="mb-2 md:mb-3">
					<span class="inline-block text-sky-500 mb-0.5">Fusion XD</span>
					<h2 class="text-sky-400 text-2xl lg:text-3xl font-bold">{data[RouteId - 1].title}</h2>
				</div>
				<!-- name - end -->

				<!-- rating - start -->
				<div class="flex items-center gap-3 mb-6 md:mb-10">
					<div class="h-7 flex items-center bg-indigo-500 text-white rounded-full gap-1 px-2">
						<span class="text-sm">4.2</span>

						<svg
							xmlns="http://www.w3.org/2000/svg"
							class="w-5 h-5"
							viewBox="0 0 20 20"
							fill="currentColor"
						>
							<path
								d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
							/>
						</svg>
					</div>

					<span class="text-gray-500 text-sm transition duration-100">56 ratings</span>
				</div>
				<!-- rating - end -->

				<!-- size - start -->
				<div class="mb-8 md:mb-10 hidden md:flex align-middle">
					<span
						class="inline-block text-gray-500 text-sm md:text-base font-semibold mb-3 mx-3 align-middle"
						>Size</span
					>

					<div class="flex flex-wrap gap-3">
						<button
							type="button"
							class="w-12 h-8 flex justify-center items-center bg-white hover:bg-gray-100 active:bg-gray-200 text-gray-800 text-sm font-semibold text-center border rounded-md transition duration-100"
							>S</button
						>
						<span
							class="w-12 h-8 flex justify-center items-center bg-white  text-sm font-semibold text-center border text-gray-800 rounded-md cursor-default"
							>M</span
						>
						<button
							type="button"
							class="w-12 h-8 flex justify-center items-center bg-white hover:bg-gray-100 active:bg-gray-200 text-gray-800 text-sm font-semibold text-center border rounded-md transition duration-100"
							>L</button
						>
						<button
							type="button"
							class="w-12 h-8 flex justify-center items-center bg-white hover:bg-gray-100 active:bg-gray-200 text-gray-800 text-sm font-semibold text-center border rounded-md transition duration-100"
							>XL</button
						>
						<button
							type="button"
							class="w-12 h-8 flex justify-center items-center bg-white hover:bg-gray-100 active:bg-gray-200 text-gray-800 text-sm font-semibold text-center border rounded-md transition duration-100"
							>2XL</button
						>
					</div>
				</div>
				<!-- size - end -->

				<!-- price - start -->
				<div class="mb-4">
					<div class="flex items-end gap-2">
						<span class="text-sky-400 text-xl md:text-2xl font-bold"
							>Rs {data[RouteId - 1].price}.00</span
						>
						<span class="text-red-300 line-through mb-0.5">Rs 1800.00</span>
					</div>

					<span class="text-gray-500 text-sm">incl. VAT plus shipping</span>
				</div>
				<!-- price - end -->

				<!-- shipping notice - start -->
				<div class="flex items-center text-gray-500 gap-2 mb-6">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="w-6 h-6"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
					>
						<path d="M9 17a2 2 0 11-4 0 2 2 0 014 0zM19 17a2 2 0 11-4 0 2 2 0 014 0z" />
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M13 16V6a1 1 0 00-1-1H4a1 1 0 00-1 1v10a1 1 0 001 1h1m8-1a1 1 0 01-1 1H9m4-1V8a1 1 0 011-1h2.586a1 1 0 01.707.293l3.414 3.414a1 1 0 01.293.707V16a1 1 0 01-1 1h-1m-6-1a1 1 0 001 1h1M5 17a2 2 0 104 0m-4 0a2 2 0 114 0m6 0a2 2 0 104 0m-4 0a2 2 0 114 0"
						/>
					</svg>

					<span class="text-sm">2-4 day shipping</span>
				</div>
				<!-- shipping notice - end -->

				<!-- buttons - start -->
				<div class="flex gap-2.5">
					<a
						href="/#formData"
						class="inline-block bg-gray-200 hover:bg-gray-300 focus-visible:ring ring-indigo-300 text-gray-500 active:text-gray-700 text-sm md:text-base font-semibold text-center rounded-lg outline-none transition duration-100 px-8 py-3"
						>Buy now</a
					>
				</div>
				<!-- buttons - end -->
			</div>
			<!-- content - end -->
		</div>
	</div>
</div>
