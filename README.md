# CKEditor Developer Edition

The popular editor for WBCE CMS

***CKEditor 4.16.1 and higher require WBCE 1.5.x !***

## FAQ: Customize CKEditor

### 1. Question:

Which files are available for template developer to customize CKEditor for WBCE?

#### Answer:

+ editor.css:
The default look of the WYSIWYG texttarea and preview.

+ editor.styles.js:
You can select the default styles from a drop-down menu in the CKEditor toolbar.

+ editor.templates.js:
You can select the standard CKE templates using the template button in the CKEditor toolbar.
Note: We recommend that you do not use CKE templates, since the WBCE template should define the various blocks and the template.

+ wb_ckconfig.js
Most configuration problems are defined here.
Toolbar configuration, behaviour on Enter / Shift+Enter, default language and so on.

The configuration files might already be in the templates folder, please have a look inside.

### 2. Question:

What is the search order for these configuration files?

#### Answer:

1) Will be called first, if available, 2) Is next, and so on!

***Do not remove or delete the default files and there content!***

editor.css
```
1) _yourInstallation/templates/_yourDefaultTemplate/editor.css
2) _yourInstallation/templates/_yourDefaultTemplate/css/editor.css
3) _yourInstallation/templates/_yourDefaultTemplate/editor/editor.css
4) _yourInstallation/templates/wb_config/editor.css
5) _yourInstallation/modules/ckeditor/ckeditor/contents.css (default)
```

editor.styles.js
```
1) _yourInstallation/templates/_yourDefaultTemplate/editor.styles.js
2) _yourInstallation/templates/_yourDefaultTemplate/js/editor.styles.js
3) _yourInstallation/templates/_yourDefaultTemplate/editor/editor.styles.js
4) _yourInstallation/templates/wb_config/editor.styles.js
5) _yourInstallation/modules/ckeditor/ckeditor/styles.js (default)
```

wb_ckconfig.js*
```
1) _yourInstallation/templates/_yourDefaultTemplate/wb_ckconfig.js
2) _yourInstallation/templates/_yourDefaultTemplate/js/wb_ckconfig.js
3) _yourInstallation/templates/_yourDefaultTemplate/editor/wb_ckconfig.js
4) _yourInstallation/templates/wb_config/wb_ckconfig.js
5) _yourInstallation/modules/ckeditor/ckeditor/config.js (default)
```

editor.templates.js
```
1) _yourInstallation/templates/_yourDefaultTemplate/editor.templates.js
2) _yourInstallation/templates/_yourDefaultTemplate/js/editor.templates.js
3) _yourInstallation/templates/_yourDefaultTemplate/editor/editor.templates.js
4) _yourInstallation/templates/wb_config/editor.templates.js
5) _yourInstallation/modules/ckeditor/wb_config/editor.templates.js (default)
```

### 3. Question:

How can I customize the CKEditor for WBCE?

#### Answer:

To customize, copy the the default files into the folder _yourInstallation/templates/_yourDefaultTemplate/ and rename it, your changes only apply to your template.
Or create a wb_config folder in _yourInstallation/templates/ and copy the default files into this folder and rename it, all changes apply to all templates.
If youe need code examples or how these files schould look like, see example files [here](https://github.com/Colinax/CKEditor/tree/developer/wb_config).

### *4. Question:

How can I remove the update notification? Is the version 4.22.1 unsafe?

#### Answer:

 When using the current version 4.22.1 of the developer edition with a custom wb_config.js, make sure to add the line
```
config.versionCheck = false;
```
to the file to avoid a unnecessary update reminder. (At CKEditor, they want you to change to the commercial CKE 4.24.0-LTS or CKE5, that's probably the main reason for this window. As far as we know the security flaws refer to plugins/parts of the editor which are not part of the CKE package for WBCE CMS.) 
