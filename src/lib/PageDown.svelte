<script>
	import { onMount } from 'svelte';

	import supabase from '$lib/db.js';

	let smalldata = {
		fullname: '',
		quantity: 1,
		size: '',
		email: '',
		selectSweat: 'Pick your favorite Sweatshirt',
		address: ''
	};
	let handleform = async () => {
		// console.log(smalldata);
		const { data, error } = await supabase.from('sweatshirtsData').insert([
			{
				fullname: smalldata.fullname,
				quantity: smalldata.quantity,
				size: smalldata.size,
				email: smalldata.email,
				selectSweat: smalldata.selectSweat,
				address: smalldata.address
			}
		]);
		smalldata.quantity = 1;
		smalldata.size = '';
		smalldata.email = '';
		smalldata.selectSweat = 'Pick your favorite Sweatshirt';
		smalldata.address = '';
	};
	let shirtdata = [];
	onMount(async () => {
		let { data, error } = await supabase.from('sweatshirtsData').select('*');
		shirtdata = data;
		// console.table(shirtdata);
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

<div class=" py-6 sm:py-8 lg:py-12" id="formData">
	<div class="max-w-screen-2xl px-4 md:px-8 mx-auto">
		<!-- text - start -->
		<div class="mb-10 md:mb-16">
			<h2 class="text-slate-100 text-3xl lg:text-6xl font-bold text-center mb-3 md:mb-2">
				Welcome to Fusion XD
			</h2>
		</div>
		<!-- text - end -->

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
				<label for="size" class="inline-block text-slate-300 text-sm sm:text-base mb-2">Size</label>
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
				<select
					class="select select-success w-full max-w-xs transition duration-100 px-3 py-2"
					bind:value={smalldata.selectSweat}
					required
				>
					<option disabled selected>Pick your favorite Sweatshirt</option>
					<option value="Drippy Drill">Drippy Drill</option>
					<option value="Fusion Cofii">Fusion Cofii</option>
					<option value="Fusion Spark">Fusion Spark</option>
					<option value="Fuzzy Lofi">Fuzzy Lofi</option>
					<option value="Classic Fuzzy ">Classic Fuzzy </option>
					<option value="Thick Art">Thick Art</option>
					<option value="Clean Flean">Clean Flean</option>
					<option value="Japanese Hoddie">Japanese Hoddie</option>
				</select>
			</div>

			<div class="sm:col-span-2">
				<label for="address" class="inline-block text-slate-300 text-sm sm:text-base mb-2"
					>Address</label
				>
				<textarea
					required
					bind:value={smalldata.address}
					name="address"
					class="w-full h-64 bg-gray-900 text-sky-500 border focus:border-2 focus:border-sky-500 rounded outline-none transition duration-100 px-3 py-2"
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
