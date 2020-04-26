CKEditor 5 classic editor build with plugins of Code Block and Alignment for Vuejs
========================================

![CKEditor 5 classic editor build screenshot](https://i.ibb.co/6m9F3Q5/ckeditor-screenshot.jpg")

## Documentation

See:

* [Installation](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/integration/installation.html) for how to install this package and what it contains.
* [Basic API](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/integration/basic-api.html) for how to create an editor and interact with it.
* [Configuration](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/integration/configuration.html) for how to configure the editor.
* [Creating custom builds](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/development/custom-builds.html) for how to customize the build (configure and rebuild the editor bundle).

## Quick start

**First, install the build from npm:
```
git clone https://github.com/trungnhvn/CKEditor-build.git
---

Copy three (03) file from: `build` folder to your own project:
---html
`node_modules\@ckeditor\ckeditor5-build-classic\build`
---
And use it in your website:

**app.js
```js
import CKEditor from '@ckeditor/ckeditor5-vue';
Vue.use( CKEditor );
---

**components
---js
import ClassicEditor from '@ckeditor/ckeditor5-build-classic';
export default {

    data() {
        return {
            'editMode': false,
            editor: ClassicEditor,
			editorData: "<p>Content of the editor.</p>",
			...

		}
	},
	...
	methods: {

        onEditorReady(editor) {
            editor.plugins.get('FileRepository').createUploadAdapter = (loader) => {
                // Configure the URL to the upload script in your back-end here!
                return new this.UploadAdapter(loader);
            };
        }
    }

}
}
---
---html
<ckeditor :editor="editor" v-model="" @ready="onEditorReady($event)" ></ckeditor>
---

**Note:** If you are planning to integrate CKEditor 5 deep into your application, it is actually more convenient and recommended to install and import the source modules directly (like it happens in `ckeditor.js`). Read more in the [Advanced setup guide](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/integration/advanced-setup.html).

## License

Licensed under the terms of [GNU General Public License Version 2 or later](http://www.gnu.org/licenses/gpl.html). For full details about the license, please check the `LICENSE.md` file or [https://ckeditor.com/legal/ckeditor-oss-license](https://ckeditor.com/legal/ckeditor-oss-license).
# CKEditor-build


