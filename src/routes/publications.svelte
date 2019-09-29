<script>
import Publication from '../components/Publication.svelte'
import pubs from './_publications.js'
</script>

<h2>Publications</h2>
{#each pubs as pub}
	<Publication {pub} />
{/each}

<style>
h2 {
	@apply text-xl mb-2 font-sans font-semibold;
}
</style>