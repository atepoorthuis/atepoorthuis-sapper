<script>
import Publication from '../components/Publication.svelte'
import pubs from './_recent_work.js'
</script>

<style>
h2 {
	@apply text-xl mt-5 mb-2 font-sans font-semibold;
}
a {
  @apply underline;
}
p {
	@apply mb-2;
}
</style>

<svelte:head>
  <title>Ate Poorthuis</title>
</svelte:head>

<div class="intro text-justify md:text-left">
	<p>
	Hi, I'm Ate Poorthuis. I'm an Assistant Professor of Big Data and Human-Environment Systems
	in the <a href="https://ees.kuleuven.be/" target="_blank" rel="noopener noreferrer">Department of
	Earth and Environmental Sciences</a>
	at <a href="https://www.kuleuven.be/english/" target="_blank" rel="noopener noreferrer">
	KU Leuven</a>. My research explores the possibilities and limitations of big data, through quantitative
	analysis and visualization, to better understand how our cities work. I have a
	particular interest in the practical application of these academic insights
	within urban planning and policy. Other projects I have worked on include the
	DOLLY Project, a repository of billions of geolocated social media, which is
	used to address the difficulties of using big data within the social sciences.
	</p>
	<p>
	Before joining KU Leuven in June 2020, I was a faculty member in the <a href="https://hass.sutd.edu.sg"
	target="_blank" rel="noopener noreferrer">Humanities, Arts and
	Social Sciences</a> at the <a href="https://www.sutd.edu.sg" target="_blank" rel="noopener noreferrer">
	Singapore University of Technology and Design</a>. 
	</p>
</div>

<div class="education">
	<h2>Education</h2>
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
	<h2>Recent Work</h2>
	<ul>
		{#each pubs as pub}
			<li class="mb-2"><Publication {pub} /></li>
		{/each}
	</ul>
	<div class="font-sans font-normal">
		⤷ <a href='/publications'>More Publications</a>
	</div>
</div>

<div class="teaching">
	<h2>Teaching</h2>
	<p class="mb-2">At the Singapore University of Technology and Design 
	I have taught the following courses:</p>
	<ul>
		<li class="mb-2">⬡ Research Methodology for Urban Analysis (MSc 
		<a href="https://urbanscience.sutd.edu.sg/" target="_blank" rel="noopener noreferrer">
		Urban Science, Policy and Planning</a>)</li>
		<li class="mb-2">⬡ Computational Urban Analysis (MSc 
		<a href="https://urbanscience.sutd.edu.sg/" target="_blank" rel="noopener noreferrer">
		Urban Science, Policy and Planning</a>)</li>
		<li class="mb-2">⬡ <a href="https://idv-2020.teaching.atepoorthuis.com/" target="_blank" rel="noopener noreferrer">
		Interactive Data Visualization</a> (MSc 
		<a href="https://urbanscience.sutd.edu.sg/" target="_blank" rel="noopener noreferrer">
		Urban Science, Policy and Planning</a>)</li>
		<li class="mb-2">⬡ Making Maps I: Introduction to Spatial Analysis and Data Visualization</li>
		<li class="mb-2">⬡ Theorizing Society, the Self, and Culture (Introduction to Social Science)</li>
	</ul>
	<p class="mb-2 mt-4">Courses I have also taught include:</p>
	<ul>
		<li class="mb-2">⬡ Introduction to Geographic Information Systems (University of Kentucky, University of Amsterdam)</li>
		<li class="mb-2">⬡ Advanced Geographic Information Systems (University of Amsterdam)</li>
		<li class="mb-2">⬡ Methods and Techniques of Spatial Planning (University of Amsterdam)</li>
	</ul>
</div>