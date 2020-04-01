# zotadd

`zotadd` is a simple (and very hacky) script to add pdf files to the library of
a locally running Zotero instance via commandline.

## usage

	zotadd foo.pdf

## integration

### thunar

It is possible to add a "custom action" in the context menu of Thunar.

Edit `~/.config/Thunar/uca.xml` inserting

	<action>
		<icon>gnome-mime-application-pdf</icon>
		<name>Add to Zotero</name>
		<unique-id>1580396221527927-1</unique-id>
		<command>PATH/zotadd %f</command>
		<description>add the file to the zotero library</description>
		<patterns>*.pdf</patterns>
		<other-files/>
	</action>

and change PATH according to your installation path.

### zathura

Add the following line to your `~/.config/zathura/zathurarc` to have the
shortcut `ctrl + shift + z` add the current pdf to Zotero:

	map <C-Z> feedkeys ":! zotadd % <Return>"
