<template>
<div id="app">
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对View的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <Add :addComment="addComment"/>
      <List :commentxs="comments" :delComment="delComment"/>
    </div>
  </div>
</div>
</template>

<script>
import Add from './components/Add.vue'
import List from './components/List.vue'

export default {
  methods: {
    addComment (comment) {
      this.comments.unshift(comment)
    },
    delComment (index) {
      console.log(index)
      this.comments.splice(index, 1)
    }
  },
  data () {
    return {
      comments: [
        {
          name: 'bbo',
          content: 'very good'
        },
        {
          name: 'tian',
          content: 'ohiiejh'
        }]
    }
  },
  components: {
    Add,
    List
  }
}
</script>

<style>
</style>
