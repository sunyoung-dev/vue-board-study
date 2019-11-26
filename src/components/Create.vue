<template>
  <div>
    <input v-model="writer" type="text" placeholder="글쓴이" />
    <input v-model="title" type="text" placeholder="제목" />
    <textarea v-model="content" type placeholder="내용"></textarea>
    <button @click="index !== undefied ? update() : write()">{{index !== undefined ? '수정' : '작성'}}</button>
  </div>
</template>

<script>
import data from '@/data'
export default {
  name: 'Create',
  data () {
    const index = this.$route.params.contentId
    return {
      data: data,
      index: index,
      writer: index !== undefined ? data[index].writer : '',
      title: index !== undefined ? data[index].title : '',
      content: index !== undefined ? data[index].content : '',
    }
  },
  methods: {
    update () {
      data[this.index].writer = this.writer
      data[this.index].title = this.title
      data[this.index].content = this.content
    },
    write () {
      this.data.push({
        writer: this.writer,
        title: this.title,
        content: this.content
      })
      this.$router.push({
        path: '/'
      })
    }
  }
}
</script>
