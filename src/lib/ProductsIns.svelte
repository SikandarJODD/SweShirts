<script>
	import Img1 from '$lib/Images/img1.png';
	import Img2 from '$lib/Images/img2.jpg';
	import Img3 from '$lib/Images/img3.jpg';
	import Img4 from '$lib/Images/img4.jpg';
	import Img5 from '$lib/Images/img5.jpg';
	import Img6 from '$lib/Images/img6.jpg';
	import Img7 from '$lib/Images/img7.jpg';
	import Img8 from '$lib/Images/img8.jpg';
	import ImgMap from './ImgMap.svelte';
	let imgData = [
		{
			id: 9,
			imgName: Img1,
			title: 'Sunny Cool'
		},
		{
			id: 16,
			imgName: Img8,
			title: 'Goku Blast'
		},
		{
			id: 15,
			imgName: Img7,
			title: 'Anyna Cuffy'
		},
		{
			id: 10,
			imgName: Img2,
			title: 'Uchia Legacy'
		},
		{
			id: 11,
			imgName: Img3,
			title: 'Pupmkin Fuffy'
		},
		{
			id: 12,
			imgName: Img4,
			title: 'Loner Wolf'
		},
		{
			id: 13,
			imgName: Img5,
			title: 'Peace Hills'
		},
		{
			id: 14,
			imgName: Img6,
			title: 'Anime Pop'
		}
	];
</script>

<!-- Tiffu -->
<div class=" py-6 sm:py-2 lg:py-1 mb-20">
	<div class="max-w-screen-xl px-4 md:px-8 mx-auto">
		<div class="grid grid-cols-2 md:grid-cols-3 gap-x-4 lg:gap-x-8 gap-y-8 lg:gap-y-12">
			<!-- person - start -->
			{#each imgData as imgd}
				<ImgMap imgName={imgd.imgName} title={imgd.title} id={imgd.id} />
			{/each}
			<!-- person - end -->
		</div>
	</div>
</div>
