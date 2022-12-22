[[<% await getJeopardyNote() %>\|<% await tp.system.suggester(['$200', '$400', '$600', '$800', '$1000'], ['$200', '$400', '$600', '$800', '$1000'], false, 'Question amount') %>]]<%*
function getJeopardyNote() {
	const files = app.vault.getFiles();
	const filePath = tp.file.path(true).split('/');
	filePath.pop();
	filePath.push('Jeopardy');
	const relativeDirPath = filePath.join('/');
	const regex = new RegExp(`^${relativeDirPath}\/.+$`);
	const jeopardyNotes = files
		.filter(file => regex.test(file.path))
		.map(file => file.name.split(/^(\s|.+)(\..+)$/)[1]);
	return tp.system.suggester(
		jeopardyNotes,
		jeopardyNotes,
		true,
		'Jeopardy question to link to',
		10
	);
}
%>