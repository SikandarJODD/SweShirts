<script>
	let name = '';
	let quantity = 1;
	let email = '';
	let size = '';
	let selectSweat = '';
	let address = '';
	let handleform = () => {
		console.log(name);
	};
</script>

<div class=" py-6 sm:py-8 lg:py-12">
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
					name="full-name"
					bind:value={name}
					class="w-full bg-gray-900 text-blue-400 border focus:border-2 focus:border-sky-500 rounded outline-none transition duration-100 px-3 py-2"
				/>
			</div>

			<div>
				<label for="quantity" class="inline-block text-slate-300 text-sm sm:text-base mb-2"
					>Quantity</label
				>
				<input
					bind:value={quantity}
					name="quantity"
					class="w-full bg-gray-900 text-blue-400 border focus:border-2 focus:border-sky-500 rounded outline-none transition duration-100 px-3 py-2"
				/>
			</div>

			<div>
				<label for="size" class="inline-block text-slate-300 text-sm sm:text-base mb-2">Size</label>
				<input
					bind:value={size}
					name="size"
					class="w-full bg-gray-900 text-blue-400 border focus:border-2 focus:border-sky-500 rounded outline-none transition duration-100 px-3 py-2"
				/>
			</div>

			<div>
				<label for="email" class="inline-block text-slate-300 text-sm sm:text-base mb-2"
					>Email</label
				>
				<input
					bind:value={email}
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
					bind:value={selectSweat}
				>
					<option disabled selected>Pick your favorite anime</option>
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
					bind:value={address}
					name="address"
					class="w-full h-64 bg-gray-900 text-sky-500 border focus:border-2 focus:border-sky-500 rounded outline-none transition duration-100 px-3 py-2"
				/>
			</div>

			<div class="sm:col-span-2 flex justify-between items-center">
				<button
					type="submit"
					class="inline-block bg-sky-600 hover:bg-sky-800  text-white text-sm md:text-lg font-semibold text-center rounded-lg outline-none transition duration-100 px-8 py-3"
					>Send</button
				>
			</div>
		</form>
		<!-- form - end -->
	</div>
</div>
