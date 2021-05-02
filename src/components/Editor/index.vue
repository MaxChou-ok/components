<template>
    <div ref="editorRef">
       editor
    </div>
</template>

<script>
import E from 'wangeditor'
export default {
    props:{
      value:String
    },
    methods:{
        initEditor(){
            const editor = new E(this.$refs.editorRef)
            editor.config.onchange = (newHtml)=>{
                this.$emit('input',newHtml)
                console.log('change之后最新的html',newHtml)
            }
            editor.create()
            editor.txt.html(this.value)
            this.$watch('value',()=>{
                editor.txt.html(this.value)
            })
        }
    },
    mounted(){
        this.initEditor()
    }
}
</script>