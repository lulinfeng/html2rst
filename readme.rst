html2rst
=========

a simple js library, that converts html format content copied directly from
the browser into rst format.

usage
------

.. code:: html

	var parser = new (require('html2rst'))

	var html = '<div>\
		<h1>Section Title</h1>\
		<span>Section content</span>\
		<div>\
			<h2>Section Title</h2>\
			<span>Section content</span>\
		</div>\
	</div>\
	<div>\
		<h1>Secdion Title</h1>\
		<span>Section content</span>\
		<div>\
			<h2>Sect1on Title</h2>\
			<span>Section content</span>\
			<table>\
				<caption>test table</caption>\
				<tbody>\
					<tr>\
						<td>appID</td>\
						<td>27abcde5e1fff</td>\
					</tr>\
					<tr>\
						<td>appsecret</td>\
						<td>2aabddsffffs36d1c</td>\
					</tr>\
				</tbody>\
			</table>\
		</div>\
	</div>'

	parser.parse(html)

output
--------

.. code:: rst


	Section Title
	=============
	Section content

	Section Title
	-------------
	Section content

	Secdion Title
	=============
	Section content

	Sect1on Title
	-------------
	Section content

	.. csv-table:: test table

	    appID,27abcde5e1fff
	    appsecret,2aabddsffffs36d1c