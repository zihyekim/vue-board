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
    <button @click="goHome()">목록으로</button>
    <button @click="goEdit()">수정</button>
    <button @click="deleteItem()">삭제</button>
  </div>
</template>

<script>
import boardList from '@/data/board'
export default {
  name:'BoardDetail',
  data(){
    const boardId = this.$route.params.boardId
    return {
      board: boardList[boardId - 1],
      boardId,
    }
  },
  methods:{
    goHome(){
      this.$router.push('/');
    },
    goEdit(){
      this.$router.push({
        name: 'BoardCreate',
        params: {
          boardId: this.boardId
        }
      })
    },
    deleteItem(){
      confirm(`삭제하시겠습니까?
삭제한 문서는 다시 되돌릴 수 없습니다.`)
      boardList.splice(this.boardId - 1 ,1);
      this.goHome();
    }
  }
}
</script>

<style>

</style>