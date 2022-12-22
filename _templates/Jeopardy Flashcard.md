---
cards-deck: <% tp.file.folder(true).split('/').join('::') %>
tags: <% await tp.system.prompt('Tag for Anki card & Obsidian note', null, true) %>, jeopardy
cssclass: jeopardy-card
---

<% await tp.system.prompt('Trivia question', null, true, true) %>
###### Hint %% fold %%
<button class="hint" onclick="showHint(this)"><span class="padding-text">⚑<br />⚑ ⚑ ⚑ ⚑ ⚑ </span>Show Hint<span class="padding-text"> ⚑ ⚑ ⚑ ⚑ ⚑<br />⚑</span></button>
<pre class="hint">
<% await tp.system.prompt('Hint for answer', null, true, true) %>
</pre>
#card
###### Answer %% fold %%
<% await tp.system.prompt('Answer to trivia question', null, true, true) %><% await getMediaFile('definition') %><%*
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