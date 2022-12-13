<template>
  <div>
    <button @click="showHtml">Show Html</button>
    <input id="document" type="file" @change="previewFiles" />
    <div class="html-content" v-html="content"></div>
  </div>
</template>

<script>
import mammoth from 'mammoth'

export default {
    name: 'HtmlPreview',
    data() {
        return {
            file: null,
            content: ''
        }
    },
    methods: {
        showHtml () {
            let reader = new FileReader();
            
            reader.onload = loadEvent => {
                const arrayBuffer = loadEvent.target.result
                mammoth.convertToHtml({
                    arrayBuffer: arrayBuffer
                }).then(res => {
                    this.content = res.value
                    console.log(res.value)
                }).catch(err => {
                    console.log(err)
                }).done()
            }
            
            reader.readAsArrayBuffer(this.file)
        },
        previewFiles (event) {
            this.file = event.target.files[0]
        }
    }
}
</script>

<style>
.html-content {
    border: 1px solid black;
}
</style>