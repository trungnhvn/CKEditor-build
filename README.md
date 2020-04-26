CKEditor 5 classic editor build with plugins of Code Block and Alignment for Vuejs
========================================

![CKEditor 5 classic editor build screenshot]
https://serving.photos.photobox.com/031924792fafb68b4e1927c0e40484381379cb025b5e46d19a4249fe3579fa78a9daf389.jpg

## Documentation

See:

* [Installation](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/integration/installation.html) for how to install this package and what it contains.
* [Basic API](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/integration/basic-api.html) for how to create an editor and interact with it.
* [Configuration](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/integration/configuration.html) for how to configure the editor.
* [Creating custom builds](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/development/custom-builds.html) for how to customize the build (configure and rebuild the editor bundle).

## Quick start

First, install the build from npm:

```bash
git clone https://github.com/trungnhvn/CKEditor-build.git
```
And then, copy three (03) file from build folder to your own project:
--html
node_modules\@ckeditor\ckeditor5-build-classic\build
---
And use it in your website:

app.js
```js
import CKEditor from '@ckeditor/ckeditor5-vue';
Vue.use( CKEditor );
---
components:
---js
<script>
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
</script>
}
---
---html
<ckeditor :editor="editor" v-model="" @ready="onEditorReady($event)" ></ckeditor>
---

**Note:** If you are planning to integrate CKEditor 5 deep into your application, it is actually more convenient and recommended to install and import the source modules directly (like it happens in `ckeditor.js`). Read more in the [Advanced setup guide](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/integration/advanced-setup.html).

## License

Licensed under the terms of [GNU General Public License Version 2 or later](http://www.gnu.org/licenses/gpl.html). For full details about the license, please check the `LICENSE.md` file or [https://ckeditor.com/legal/ckeditor-oss-license](https://ckeditor.com/legal/ckeditor-oss-license).
# CKEditor-build


