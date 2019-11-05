<template>
    <div>
        <input v-model="writer" type="text" placeholder="글쓴이"/>
        <input v-model="title" type="text" placeholder="제목"/>
        <textarea v-model="content" type="" placeholder="내용"></textarea>
        <button @click="save">저장</button>
    </div>
</template>

<script>
import data from '@/data'
export default {
    name: 'Create',
    data() {
        return {
            data: data,
            writer: '',
            title: '',
            content: ''
        }
    },
    methods: {
        save() {
            this.data.push({
                writer: this.writer,
                title: this.title,
                content: this.content
            })
            this.$router.push({
                path: '/'
            });
        }
    }
}
</script>