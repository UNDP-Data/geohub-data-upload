<script lang="ts">
	import type { SDG } from '../interfaces';

	export let selectedSDG: SDG;

	let sdgs: SDG[] = [
		{
			number: 1,
			name: 'NO POVERTY'
		},
		{
			number: 2,
			name: 'ZERO HUNGER'
		},
		{
			number: 3,
			name: 'GOOD HEALTH AND WELLBEING'
		},
		{
			number: 4,
			name: 'QUALITY EDUCATION'
		},
		{
			number: 5,
			name: 'GENDER EQUALITY'
		},
		{
			number: 6,
			name: 'CLEAN WATER AND SANITATION'
		},
		{
			number: 7,
			name: 'AFFORDABLE AND CLEAN ENERGY'
		},
		{
			number: 8,
			name: 'DECENT WORK AND ECONOMIC GROWTH'
		},
		{
			number: 9,
			name: 'INDUSTRY, INOVATION AND INFRASTRUCTURE'
		},
		{
			number: 10,
			name: 'REDUCED INEQUALITIES'
		},
		{
			number: 11,
			name: 'SUSATAINABLE CITIES AND COMMUNITES'
		},
		{
			number: 12,
			name: 'RESPONSIBLE CONSUMPTION AND PRODUCTION'
		},
		{
			number: 13,
			name: 'CLIMATE ACTION'
		},
		{
			number: 14,
			name: 'LIFE BELOW WATER'
		},
		{
			number: 15,
			name: 'LIFE ON LAND'
		},
		{
			number: 16,
			name: 'PEACE, JUSTICE AND STRONG INSTITUTIONS'
		},
		{
			number: 17,
			name: 'PARTNERSHIPS FOR GOALS'
		}
	];

	const handleSDGSelect = (no: number) => {
		selectedSDG = sdgs.find((sdg) => sdg.number === no);
	};
</script>

<div class="columns mx-5 is-mobile is-multiline is-centered">
	{#each sdgs as sdg}
		<div
			class="column p-1 m-0 sdg-icon {`${
				selectedSDG && sdg.number === selectedSDG.number ? 'is-active' : ''
			}`}"
		>
			<figure
				class="image is-128x128"
				on:click={() => {
					handleSDGSelect(sdg.number);
				}}
			>
				<!-- svelte-ignore a11y-missing-attribute -->
				<img src={`../sdgs/${sdg.number}.png`} />
			</figure>
		</div>
	{/each}
</div>

<style lang="scss">
	.sdg-icon {
		cursor: pointer;
	}

	.is-active {
		background-color: yellow;
	}
</style>
