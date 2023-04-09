<script>
	import supabase  from '$lib/db.js';
	let dataObj = {
        id: '',
		first_name: '',
		last_name: '',
		email: '',
		img_url: '',
		shirt_title: ''
	};
	let handleData = async () => {
		if (
			dataObj.first_name != '' &&
			dataObj.last_name != '' &&
			dataObj.email != '' &&
			dataObj.img_url != ''
		) {
            try{
                const { data, error } = await supabase.from('swe-shirt-users').insert({
                    first_name: dataObj.first_name,
                    last_name: dataObj.last_name,
                    email: dataObj.email,
                    img_url: dataObj.img_url,
                    shirt_title: dataObj.shirt_title
                });
                alert('Your Swe-Shirt has been uploaded');
                dataObj = {
                    id: '',
                    first_name: '',
                    last_name: '',
                    email: '',
                    img_url: '',
                    shirt_title: ''
                };
            }
            catch(err){
                console.log(err);
            }
		} else {
			alert('Please fill all the fields');
		}
	};
</script>

<div class="bg-white py-6 sm:py-8 lg:py-12">
	<div class="mx-auto max-w-screen-2xl px-4 md:px-8">
		<!-- text - start -->
		<div class="mb-10 md:mb-16">
			<h2 class="mb-4 text-center text-2xl font-bold text-gray-800 md:mb-6 lg:text-3xl">
				Upload Your <span class="text-blue-700">Swe-Shirt</span>
			</h2>
		</div>
		<!-- text - end -->

		<!-- form - start -->
		<form on:submit|preventDefault={handleData} class="mx-auto grid max-w-screen-md gap-4 sm:grid-cols-2">
			<div>
				<label for="first-name" class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
					>First name*</label
				>
				<input
					name="first-name"
					class="w-full  rounded border bgCol px-3 py-2 text-gray-800 outline-none  transition duration-100 "
					bind:value={dataObj.first_name}
					required
				/>
			</div>

			<div>
				<label for="last-name" class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
					>Last name*</label
				>
				<input
					name="last-name"
					class="w-full rounded border bgCol px-3 py-2 text-gray-800 outline-none  transition duration-100"
					bind:value={dataObj.last_name}
					required
				/>
			</div>
			<div>
				<label for="shirt_title" class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
					>T-Shirt Title*</label
				>
				<input
					name="shirt_title"
					class="w-full rounded border bgCol px-3 py-2 text-gray-800 outline-none  transition duration-100"
					bind:value={dataObj.shirt_title}
					required
				/>
			</div>
			<div>
				<label for="email" class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
					>Email*</label
				>
				<input
					name="email"
					class="w-full rounded border bgCol px-3 py-2 text-gray-800 outline-none  transition duration-100"
					bind:value={dataObj.email}
					required
				/>
			</div>

			<div class="sm:col-span-2">
				<label for="imgTag" class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
					>T-Shirt ( Img ) Url</label
				>
				<input
					name="imgTag"
					class="w-full rounded border bgCol px-3 py-2 text-gray-800 outline-none  transition duration-100"
					bind:value={dataObj.img_url}
					required
				/>
			</div>
			<div class="flex items-center justify-between sm:col-span-2">
				<button
					class="inline-block rounded-lg bg-indigo-500 px-8 py-3 text-center text-sm font-semibold text-white outline-none  transition duration-100 hover:bg-indigo-600 focus-visible:ring active:bg-indigo-700 md:text-base"
					type="submit">Send</button
				>
			</div>
		</form>
	</div>
</div>

<style>
	.bgCol {
		background: rgba(0, 22, 62, 0.949);
		color: rgb(64, 255, 214);
	}
</style>
