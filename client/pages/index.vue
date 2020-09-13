<template>
  <section class="container">
      <quill-editor
        class="quill-editor"
        ref="editor"
        v-model="content"
        :options="editorOption"
        @blur="onEditorBlur($event)"
        @focus="onEditorFocus($event)"
        @ready="onEditorReady($event)"
      />
  </section>
</template>

<script>
export default {
  name: 'quill-example-nuxt',
  data () {
    return {
      content: '<p>I am Example</p>',
      editorOption: {
        // Some Quill options...
        theme: 'snow',
        modules: {
          toolbar: [
            ['bold', 'italic', 'underline', 'strike'],        // toggled buttons
            ['blockquote', 'code-block'],

            [{ 'list': 'ordered'}, { 'list': 'bullet' }],
            [{ 'indent': '-1'}, { 'indent': '+1' }],          // outdent/indent
            [{ 'direction': 'rtl' }],                         // text direction

            [{ 'header': [1, 2, 3, 4, 5, 6, false] }],

            [{ 'color': [] }, { 'background': [] }],          // dropdown with defaults from theme
            [{ 'align': [] }],

            ['clean']                                         // remove formatting button
          ]
        }
      }
    }
  },
  mounted() {

  },
  methods: {
    onEditorBlur(editor) {
      console.log('editor blur!', editor)
    },
    onEditorFocus(editor) {
      console.log('editor focus!', editor)
    },
    onEditorReady(editor) {
      console.log('editor ready!', editor)
    }
  }
}
</script>

<style scoped>
.container {
  width: 60%;
  margin: 0 auto;
  padding: 50px 0;
}

.quill-editor {

}
</style>
