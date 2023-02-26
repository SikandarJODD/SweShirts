<!-- Use in ProductIns.svelte  -->
<script>
	export let imgName, title, id;
</script>

<div>
	<div class="h-48 sm:h-60 md:h-96 bg-gray-100 overflow-hidden rounded-lg shadow-lg mb-2 sm:mb-4">
		<!-- svelte-ignore a11y-img-redundant-alt -->
		<a href="/products/{id}">
			<img
				src={imgName}
				loading="lazy"
				alt="Photo by Radu Florin"
				class="w-full h-full  object-cover object-center hover:scale-110 transition duration-200"
			/>
		</a>
	</div>

	<div>
		<div class="text-sky-500 md:text-2xl font-bold">{title}</div>
	</div>
</div>
