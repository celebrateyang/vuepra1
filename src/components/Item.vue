<template>
  <div>
    <li class="list-group-item">
      <div class="handle">
        <a href="javascript:;" @click="delItem">删除</a>
      </div>
      <p class="user"><span >{{comment.name}}</span><span>说:</span></p>
      <p class="centence">{{comment.content}}</p>
    </li>
  </div>
</template>

<script>
  export default{
    props: {
      comment: Object,
      delComment: Function,
      index: Number
    },
    methods: {
      delItem () {
        const {index, comment} = this
       if (window.confirm(`确认删除${comment.name}的评论`)){
            console.log(index)
            this.delComment(index)
        }
      }
    }
  }
</script>

<style>
  li {
    transition: .5s;
    overflow: hidden;
  }

  .handle {
    width: 40px;
    border: 1px solid #ccc;
    background: #fff;
    position: absolute;
    right: 10px;
    top: 1px;
    text-align: center;
  }

  .handle a {
    display: block;
    text-decoration: none;
  }

  .list-group-item .centence {
    padding: 0px 50px;
  }

  .user {
    font-size: 22px;
  }
</style>
