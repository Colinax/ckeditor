# CKEditor Standard Edition

## The popular editor for WBCE CMS
Contains CKEditor 4.13.1 standard package and some other plugins, CKEditor allows content editing and can be integrated into modules.

***CKEditor 4.12.0.1 and higher require WBCE 1.4 !***

## FAQ: Customize CKEditor

### Question:

Which files are available to customize CKEditor for WBCE?

#### Answer:

+ editor.css:
The default look of the WYSIWYG texttarea and preview.

+ editor.styles.js:
You can select the default styles from a drop-down menu in the CKEditor toolbar.

The configuration files might already be in the templates folder, please have a look inside.

### question:

How can I customize the CKEditor for WBCE?

#### Answer:

To customize, copy the files from _yourInstallation/modules/ckeditor/ckeditor/ into the folder _yourInstallation/templates/_yourDefaultTemplate/, your changes only apply to your template.
Or create a wb_config folder in _yourInstallation/templates/ and copy the files into this folder, all changes apply to all templates.
You can also see the old wb_config files from the [archive branch](https://github.com/Colinax/CKEditor/tree/archive/wb_config).

### Question:

What is the workflow when reading CKEditor files?

#### Answer:

1) Will be called first, if available, 2) Is next, and so on!

Search order for configuration files

editor.css

1) _yourInstallation/templates/_yourDefaultTemplate/editor.css
2) _yourInstallation/templates/_yourDefaultTemplate/css/editor.css
3) _yourInstallation/templates/_yourDefaultTemplate/editor/editor.css
4) _yourInstallation/templates/wb_config/editor.css
5) _yourInstallation/modules/ckeditor/ckeditor/contents.css

editor.styles.js

1) _yourInstallation/templates/_yourDefaultTemplate/editor.styles.js
2) _yourInstallation/templates/_yourDefaultTemplate/js/editor.styles.js
3) _yourInstallation/templates/_yourDefaultTemplate/editor/editor.styles.js
4) _yourInstallation/templates/wb_config/editor.styles.js
5) _yourInstallation/modules/ckeditor/ckeditor/styles.js