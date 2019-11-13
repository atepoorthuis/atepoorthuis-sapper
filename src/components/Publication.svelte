<script>
export let pub

function formatAuthor (authors, firstAuthorReverse = true) {
  let formattedAuthors = ''
  for (let index = 0; index < authors.length; index++) {
    const author = authors[index]
    let html = ''
    if (index === 0 && firstAuthorReverse) {
      html += author.family + ', '
      html += author.given.slice(0, 1) + '.'
    } else {
      html += author.given.slice(0, 1) + '. '
      html += author.family
    }
    if (author.family === 'Poorthuis') {
      html = `<span class="font-semibold">${html}</span>`
    }
    if (authors.length > 1) {
      if (index === authors.length - 2) {
        html += ' and '
      }
      if (index < authors.length - 2) {
        html += ', '
      }
    }
    formattedAuthors += html
  }
  return formattedAuthors
}

function formatArticle (pub) {
  let output = `<span class="italic">${pub['container-title']}</span>`
  if (pub.volume) {
    output += ` (${pub.volume})`
  }
  if (pub.issue) {
    output += ` ${pub.issue}`
  }
  if (pub.page) {
    output += `, pp. ${pub.page}`
  }
  output += '.'
  if (pub.URL) {
    output += ` <button class="border pl-1 pr-1 rounded"><a href="${pub.URL}" target="_blank" rel="noopener noreferrer">doi</a></button>`
  }
  return output
}

function formatChapter (pub) {
  let output = 'In: '
  if (pub.editor) {
    output += formatAuthor(pub.editor, false)
    output += ' (Eds.), '
  }
  output += `<span class="italic">${pub['container-title']}</span>. `
  if (pub['publisher-place']) {
    output += `${pub['publisher-place']}: `
  }
  if (pub['publisher']) {
    output += pub['publisher']
  }
  output += '.'
  if (pub.URL) {
    output += ` <button class="border pl-1 pr-1 rounded"><a href="${pub.URL}" target="_blank" rel="noopener noreferrer">isbn</a></button>`
  }
  return output
}

function formatPub (pub) {
  const authors = formatAuthor(pub.author)
  let output = `${authors} (${pub.issued['date-parts'][0]}). 
  ${pub.title} `
  if (pub.type === 'article-journal') {
    output += formatArticle(pub)
  }
  if (pub.type === 'chapter') {
    output += formatChapter(pub)
  }
  if (pub.preprint) {
    output += ` <button class="border pl-1 pr-1 rounded"><a href="${pub.preprint}" target="_blank" rel="noopener noreferrer">preprint</a></button>`
  }
  if (pub.code) {
    output += ` <button class="border pl-1 pr-1 rounded"><a href="${pub.code}" target="_blank" rel="noopener noreferrer">code & data</a></button>`
  }
  if (pub.interactive) {
    output += ` <button class="border pl-1 pr-1 rounded"><a href="${pub.interactive}" target="_blank" rel="noopener noreferrer">interactive</a></button>`
  }
  return output
}
</script>

{@html formatPub(pub)}