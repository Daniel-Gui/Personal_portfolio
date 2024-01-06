<script>
	/** @type {import("@prismicio/client").Content.HeaderSlice} */
	import { PrismicImage, PrismicRichText } from '@prismicio/svelte';
	import { ArrowDownRight } from 'lucide-svelte';

	/**
	 * @type {{ slice_type: any; variation: any; primary: { title_presentation: any; location_description: any; Image_represents: any; }; }}
	 */
	export let slice;
</script>

<section class="bg-black" data-slice-type={slice.slice_type} data-slice-variation={slice.variation}>
	<div class="container relative flex h-screen justify-center">
		<div
			class="absolute top-64 z-10 -mr-[530px] inline-flex h-auto flex-col items-start gap-4 text-white"
		>
			<ArrowDownRight strokeWidth="1" class="h-12 w-12" />
			<h1 class="text-3xl"><PrismicRichText field={slice.primary.title_presentation} /></h1>
			<div class="bg- rounded-full bg-white/20 px-8 py-3 backdrop-blur-sm">
				<h2><PrismicRichText field={slice.primary.location_description} /></h2>
			</div>
		</div>
		<PrismicImage class="absolute bottom-0 h-auto w-3/5" field={slice.primary.Image_represents} />
	</div>
</section>
