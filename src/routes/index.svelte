<!-- <script context="module">
	export async function preload (page, session) {
	  const res = await this.fetch(`publications.json`)
	  const pubs = await res.json()
	  return { pubs }
	}
</script> -->

<script>
import pubs from './_publications.js'

function formatPub (pub) {
  let authors = ''
  for (let index = 0; index < pub.author.length; index++) {
    const author = pub.author[index]
    let html = ''
    if (index === 0) {
      html += author.family + ', '
      html += author.given.slice(0, 1) + '.'
    } else {
      html += author.given.slice(0, 1) + '. '
      html += author.family
    }
    if (author.family === 'Poorthuis') {
      html = `<span class="font-semibold">${html}</span>`
    }
    if (pub.author.length > 1) {
      if (index === pub.author.length - 2) {
        html += ' and '
	  }
	  if (index < pub.author.length - 2) {
        html += ', '
      }
    }
    authors += html
  }
  return `<ul>${authors} (${pub.issued['date-parts'][0]}). 
  ${pub.title} <span class="italic">${pub['container-title']}</span> 
  (${pub.volume}) ${pub.issue}, ${pub.page}. 
  <button class="border pl-1 pr-1 rounded"><a href=${pub.URL}>doi</a></button>
  <button class="border pl-1 pr-1 rounded"><a href=${pub.preprint}>pdf</a></button>
  </ul>`
}
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
	<a href="#publications" name="publications"><h2>Publications</h2></a>
	{#each pubs as pub}
		<p>{@html formatPub(pub)}</p>
	{/each}
</div>

<!-- <a href="#projects" name="projects"><h2>Projects</h2></a> -->

<!-- <a href="#teaching" name="teaching"><h2>Teaching</h2></a> -->
