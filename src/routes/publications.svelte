<script>
import Publication from '../components/Publication.svelte'
import pubs from './_publications.js'
</script>

<h2>Publications</h2>
<ol class="list-decimal list-inside" reversed>
	{#each pubs as pub}
		<li class="mb-2"><Publication {pub} /></li>
	{/each}
</ol>
<style>
h2 {
	@apply text-xl mb-2 font-sans font-semibold;
}
</style>