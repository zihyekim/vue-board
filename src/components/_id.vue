<template>
  <div>
    <table>
      <tbody>
          <tr>
            <td>제목</td> <td>{{ board.title}}</td>
          </tr>
          <tr>
            <td>분류</td> <td>{{ board.field}}</td>
          </tr>
          <tr>
            <td>작성자</td> <td>{{ board.writer}}</td>
          </tr>
          <tr>
            <td>작성일</td> <td>{{ board.date}}</td>
          </tr>
          <tr>
            <td>내용</td> <td>{{ board.content}}</td>
          </tr>
      </tbody>
    </table>
    <button @click="$router.push('/')">목록으로</button>
  </div>
</template>

<script>
import boardList from '@/data/board'
export default {
  name:'BoardDetail',
  data(){
    const boardId = this.$route.params.boardId - 1
    return {
      board: boardList[boardId]
    }
  }
}
</script>

<style>

</style>