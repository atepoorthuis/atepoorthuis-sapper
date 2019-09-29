<script>
import Publication from '../components/Publication.svelte'
import pubs from './_publications.js'
</script>

<style>
h2 {
	@apply text-xl mt-4 mb-2 font-sans font-semibold;
}
</style>

<svelte:head>
  <title>Ate Poorthuis</title>
</svelte:head>

<div class="intro text-justify md:text-left">
	<p>
	Hi, I'm Ate Poorthuis. I'm an Assistant Professor in the Humanities, Arts and
	Social Sciences at Singapore University of Technology and Design. My research
	explores the possibilities and limitations of big data, through quantitative
	analysis and visualization, to better understand how our cities work. I have a
	particular interest in the practical application of these academic insights
	within urban planning and policy. Other projects I have worked on include the
	DOLLY Project, a repository of billions of geolocated social media, which is
	used to address the difficulties of using big data within the social sciences.
	</p>
</div>

<div class="education">
	<a href="#education" name="education"><h2>Education</h2></a>
	<div class="mb-3">
		<p>⬡ PhD in Geography</p>
		<p class="italic">University of Kentucky</p>
	</div>
	<div class="mb-3">
		<p>⬡ MSc (Research) in Metropolitan Studies</p>
		<p class="italic">University of Amsterdam</p>
	</div>
	<div class="mb-3">
		<p>⬡ BSc in Human Geography</p>
		<p class="italic">University of Amsterdam</p>
	</div>
</div>

<div class="publications">
	<a href="#publications" name="publications"><h2>Recent Publications</h2></a>
	{#each pubs as pub}
		<Publication {pub} />
	{/each}
</div>

<!-- <a href="#projects" name="projects"><h2>Projects</h2></a> -->

<!-- <a href="#teaching" name="teaching"><h2>Teaching</h2></a> -->
