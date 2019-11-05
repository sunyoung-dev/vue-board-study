<template>
    <div>
        <table>
            <tr>
                <td>글쓴이</td>
                <td>제목</td>
                <td>내용</td>
            </tr>
            <tr :key="index" v-for="(item, index) in items">
                <td>{{ item.writer }}</td>
                <td>{{ item.title }}</td>
                <td>{{ item.content }}</td>
            </tr>
            <button @click="write">글쓰기</button>
        </table>
    </div>
</template>

<script>
import data from '@/data'
export default {
    name: 'Read',
    data () {
        return {
            items: data
        }
    },
    methods: {
        write () {
            this.$router.push({
                path: '/create'
            });
        }
    }
}

</script>