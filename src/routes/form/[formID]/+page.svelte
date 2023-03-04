<script>
	import Img1 from '$lib/img1.jpg';
	import Img2 from '$lib/img2.jpg';
	import Img3 from '$lib/img3.jpg';
	import Img4 from '$lib/img4.jpg';
	import Img5 from '$lib/img5.jpg';
	import Img6 from '$lib/img6.jpg';
	import Img7 from '$lib/img7.jpg';
	import Img8 from '$lib/img8.jpg';
	import Img9 from '$lib/Images/img1.png';
	import Img10 from '$lib/Images/img2.jpg';
	import Img11 from '$lib/Images/img3.jpg';
	import Img12 from '$lib/Images/img4.jpg';
	import Img13 from '$lib/Images/img5.jpg';
	import Img14 from '$lib/Images/img6.jpg';
	import Img15 from '$lib/Images/img7.jpg';
	import Img16 from '$lib/Images/img8.jpg';

	import { page } from '$app/stores';
	import { onMount } from 'svelte';

	$: RouteId = $page.params.formID;
	$: overAll = RouteId - 1;
	$: console.log(RouteId);
	import supabase from '$lib/db.js';
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
	let smalldata = {
		fullname: '',
		quantity: 1,
		size: '',
		email: '',
		address: ''
	};
	$: sweShirtSelection = data[overAll].title;
	let handleform = async () => {
		// console.log(smalldata);
		const { data, error } = await supabase.from('sweatshirtsData').insert([
			{
				fullname: smalldata.fullname,
				quantity: smalldata.quantity,
				size: smalldata.size,
				email: smalldata.email,
				selectSweat: sweShirtSelection,
				address: smalldata.address
			}
		]);
		smalldata.quantity = 1;
		smalldata.size = '';
		smalldata.email = ' ';
		smalldata.address = '';
	};
	let shirtdata = [];
	onMount(async () => {
		let { data, error } = await supabase.from('sweatshirtsData').select('*');
		shirtdata = data;
		console.table(shirtdata);
	});
	let value = 0;
	let activeToast = () => {
		value = 1;
		setTimeout(() => {
			smalldata.fullname = '';
			value = 0;
		}, 3500);
	};
</script>

<section>
	<div class="mb-3 md:mb-2 md:mt-5">
		<h2 class="text-slate-100 text-3xl lg:text-6xl font-bold text-center mb-3 md:mb-2">
			Welcome to Fusion XD
		</h2>
	</div>
</section>
<section class="flex flex-col md:flex-row">
	<div class="box md:w-1/2 mx-3 md:mx-10">
		<div class="py-5 sm:py-8">
			<div class="flex flex-wrap gap-4 lg:gap-6 sm:py-2.5">
				<div class="sm:-my-2.5 flex justify-center w-full md:inline-block md:w-fit">
					<!-- svelte-ignore a11y-img-redundant-alt -->
					<img
						src={data[RouteId - 1].imgSrc}
						alt="Photo by Thái An"
						class="w-56 h-56  md:w-72 md:h-96 rounded-lg object-cover object-center group-hover:scale-110 transition duration-200"
					/>
				</div>

				<div class="flex flex-col">
					<div class="flex flex-col">
						<div
							class="inline-block   text-slate-300 hover:text-gray-500 text-xl lg:text-3xl font-bold transition duration-100 mb-1"
						>
							{data[RouteId - 1].title}
						</div>

						<div>
							<span class="block text-slate-300 md:text-lg font-bold mb-1"
								>Rs.{data[RouteId - 1].price}</span
							>

							<span class="flex items-center text-gray-500 text-sm gap-1">
								<svg
									xmlns="http://www.w3.org/2000/svg"
									class="w-5 h-5 text-green-500"
									fill="none"
									viewBox="0 0 24 24"
									stroke="currentColor"
								>
									<path
										stroke-linecap="round"
										stroke-linejoin="round"
										stroke-width="2"
										d="M5 13l4 4L19 7"
									/>
								</svg>

								In stock
							</span>
						</div>
					</div>

					<div
						class="w-full sm:w-auto flex justify-center border-t sm:border-none pt-4 sm:pt-0 px-5 md:px-0"
					>
						<div class="flex flex-col items-start gap-2">
							<button
								class="text-indigo-500 hover:text-indigo-600 active:text-indigo-700 text-sm font-semibold select-none transition duration-100"
								>Quantity</button
							>
							<div class="w-28 h-12 flex border rounded overflow-hidden">
								<input
									bind:value={smalldata.quantity}
									type="number"
									class="w-full bg-transparent focus:ring ring-inset ring-indigo-300 outline-none transition   duration-100 px-4 py-2"
								/>

								<div class="flex flex-col  border-l divide-y">
									<button
										on:click={() => {
											smalldata.quantity++;
										}}
										class="w-6 flex justify-center items-center flex-1 bg-slate-800 text-sky-400 hover:bg-slate-700 active:bg-gray-200 leading-none select-none transition duration-100"
										>+</button
									>
									<button
										on:click={() => {
											if (smalldata.quantity == 1) {
												smalldata.quantity = 1;
											} else {
												smalldata.quantity--;
											}
										}}
										class="w-6 flex justify-center items-center flex-1 bg-slate-800 text-sky-400 hover:bg-slate-700 text-2xl active:bg-gray-200 leading-none select-none transition duration-100"
										>-</button
									>
								</div>
							</div>
						</div>

						<div class=" sm:pt-2 ml-4 md:ml-8 lg:ml-10 ">
							<div class="block text-sky-400 md:text-xl font-bold">
								Rs. {data[RouteId - 1].price * smalldata.quantity}
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
	<!-- Product End -->

	<div class=" py-6 sm:py-8 lg:py-12 md:max-w-xl" id="formData">
		<div class="max-w-screen-2xl px-4 md:px-8 mx-auto">
			<!-- form - start -->
			<form
				class="max-w-screen-md grid sm:grid-cols-2 gap-4 mx-auto mb-20"
				on:submit|preventDefault={handleform}
			>
				<div>
					<label for="full-name" class="inline-block text-slate-300 text-sm sm:text-base mb-2"
						>Full Name</label
					>
					<input
						required
						name="full-name"
						bind:value={smalldata.fullname}
						class="w-full bg-gray-900 text-blue-400 border focus:border-2 focus:border-sky-500 rounded outline-none transition duration-100 px-3 py-2"
					/>
				</div>
				<!-- code  -->
				<div>
					<label for="quantity" class="inline-block text-slate-300 text-sm sm:text-base mb-2"
						>Quantity</label
					>
					<input
						required
						bind:value={smalldata.quantity}
						name="quantity"
						class="w-full bg-gray-900 text-blue-400 border focus:border-2 focus:border-sky-500 rounded outline-none transition duration-100 px-3 py-2"
					/>
				</div>

				<div>
					<label for="size" class="inline-block text-slate-300 text-sm sm:text-base mb-2"
						>Size</label
					>
					<input
						required
						bind:value={smalldata.size}
						name="size"
						class="w-full bg-gray-900 text-blue-400 border focus:border-2 focus:border-sky-500 rounded outline-none transition duration-100 px-3 py-2"
					/>
				</div>

				<div>
					<label for="email" class="inline-block text-slate-300 text-sm sm:text-base mb-2"
						>Email</label
					>
					<input
						required
						bind:value={smalldata.email}
						name="email"
						class="w-full bg-gray-900 text-blue-400 border focus:border-2 focus:border-sky-500 rounded outline-none transition duration-100 px-3 py-2"
					/>
				</div>

				<div class="sm:col-span-2">
					<label for="subject" class="inline-block text-slate-300 text-sm sm:text-base mb-2"
						>Select favorite Sweatshirt</label
					>

					<input
						disabled
						bind:value={data[RouteId - 1].title}
						name="subject"
						class="w-full bg-gray-900 text-blue-400 border focus:border-2 focus:border-sky-500 rounded outline-none transition duration-100 px-3 py-2"
					/>
				</div>

				<div class="sm:col-span-2">
					<label for="address" class="inline-block text-slate-300 text-sm sm:text-base mb-2"
						>Address</label
					>
					<textarea
						required
						bind:value={smalldata.address}
						name="address"
						class="w-full h-32 bg-gray-900 text-sky-500 border focus:border-2 focus:border-sky-500 rounded outline-none transition duration-100 px-3 py-2"
					/>
				</div>

				<div class="sm:col-span-2 flex justify-between items-center">
					<button
						type="submit"
						on:click={activeToast}
						class="inline-block bg-sky-600 hover:bg-sky-800  text-white text-sm md:text-lg font-semibold text-center rounded-lg outline-none transition duration-100 px-8 py-3"
						>Send</button
					>
				</div>
			</form>
			<!-- form - end -->
		</div>
	</div>

	{#if value == 1 && smalldata.fullname != ''}
		<div class="toast toast-top toast-end md:toast-end md:toast-bottom">
			<div class="alert alert-success">
				<div>
					<span
						>Dear <strong>{smalldata.fullname}</strong> Order is Placed, Will Be Delivered in 2 Days
						<br />
						<i>Thankyou for Shopping with us</i>
					</span>
				</div>
			</div>
		</div>
	{/if}
</section>
