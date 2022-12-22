---
cards-deck: <% tp.file.folder(true).split('/').join('::') %>
tags: <% await tp.system.prompt('Tag for Anki card & Obsidian note', null, true) %>, vocab
cssclass: vocab-card
---

<button class="hint" onclick="showHint(this)"><span class="padding-text">⚑<br />⚑ ⚑ ⚑ ⚑ ⚑ </span>Show Hint<span class="padding-text"> ⚑ ⚑ ⚑ ⚑ ⚑<br />⚑</span></button>
<pre class="hint">
<% await tp.system.prompt('Hint for answer', null, true, true) %>
</pre>
#card
<% await tp.system.prompt('Definition of vocab term', null, true, true) %><% await getMediaFile('definition') %><%*
function getMediaFile(section) {
	const files = app.vault.getFiles();
	const mediaFiles = files
		.filter(file => /^_media\/.+$/.test(file.path))
		.map(file => file.name);
	return tp.system.suggester(
		mediaFiles,
		mediaFiles,
		false,
		`Optional media file for ${section}. Press escape to skip.`,
		10
	).then(mediaFile => mediaFile
		? `\n![[${mediaFile}]]`
		: ''
	);
}
%>