<script>
export let pub

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
  return `
  <ul class="mb-2">${authors} (${pub.issued['date-parts'][0]}). 
  ${pub.title} <span class="italic">${pub['container-title']}</span> 
  (${pub.volume}) ${pub.issue}, pp. ${pub.page}. 
  <button class="border pl-1 pr-1 rounded"><a href=${pub.URL}>doi</a></button>
  <button class="border pl-1 pr-1 rounded"><a href=${pub.preprint}>preprint</a></button>
  </ul>
  `
}
</script>

{@html formatPub(pub)}