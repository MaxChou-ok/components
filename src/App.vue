<template>
<div>

<div>
  editor
  <Editor v-model="content"/>

</div>


  <div>
    button
    <h-button>default</h-button>
    <h-button type="primary">primary</h-button>
    <h-button type="danger">danger</h-button>

     <h-button>default</h-button>
    <h-button size="small">small</h-button>
    <h-button size="large">large</h-button>

     <h-button>default</h-button>
    <h-button type="primary" size="small">small</h-button>
    <h-button type="danger" size="large">large</h-button>

    <!-- 未设置的错误传值测试 -->
    <h-button size="big"></h-button>

    <!-- <h-button @click.native="handle">clickme</h-button> -->

    <!-- 父子通信绑定 -->
    <h-button @click="clickHandle">clickme</h-button>
  </div>
</div>

  
  
</template>

<script>
import HButton from '@/components/button'
import Editor from '@/components/Editor'
export default {
  components:{
    HButton,
    Editor
  },
  data(){
  return {
    content:'我是编辑器'
  }
  },
  methods:{
    clickHandle(e){
       console.log('click',e)
    }
  }
}
</script>