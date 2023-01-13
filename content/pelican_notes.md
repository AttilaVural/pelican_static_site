Title: Pelican notes
Date: 2019-10-20 11:22
Category: Python
Author: Attila Vural
Tags: pelican, tutorial



if you add a code block in the top most of the page, the page load the code block wrong and execture the html code.

You cannot add the mermaid plugin to pelican. 
More specifially, pelican uses the python markdown package and mermaid is not on the list of supported extensions: https://python-markdown.github.io/extensions/
it is not even on the list of unsupported extensions: https://github.com/Python-Markdown/markdown/wiki/Third-Party-Extensions

otherwise it would simply have been a question of manually configuring the markdown extension by adding:

	MARKDOWN = {
		'extension_configs': {
			'markdown.extensions.codehilite': {'css_class': 'highlight'},
			'markdown.extensions.extra': {},
			'markdown.extensions.meta': {},
			'markdown.extensions.md_mermaid': {},
		},
		'output_format': 'html5',
	}

which is just the default included markdown extensions (see https://docs.getpelican.com/en/latest/settings.html) and the mermaid one included in the bottom. I interpolated this from this page for the python markdown package: https://pypi.org/project/md-mermaid/.

but somehow it doesn't work and the pelican compilar in CMD gives this error when recompiling: "No module named 'markdown.extensions.md_mermaid'". I just dont think it is supported.




