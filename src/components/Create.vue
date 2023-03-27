<template>
  <div class="board-create">
    <table>
      <tbody>
        <tr>
          <td>작성자</td>
          <td><input type="text" v-model="newData.writer"></td>
        </tr>
        <tr>
          <td>분류</td>
          <td><select name="" id="" v-model="newData.field">
            <option value="공지">공지</option>
            <option value="FAQ">FAQ</option>
            </select></td>
        </tr>
        <tr>
          <td>제목</td>
          <td><input type="text" v-model="newData.title"></td>
        </tr>
        <tr>
          <td>내용</td>
          <td><input type="textarea" v-model="newData.content"></td>
        </tr>
      </tbody>
    </table>
    <button @click="save()">저장</button>
  </div>
</template>

<script>
import boardList from '@/data/board'

export default {
  name:'BoardCreate',
  data:() =>({
    boardList,
    newData:{
      id: boardList.length + 1,
      writer:'',
      field:'',
      title:'',
      content:'',
    },
  }),
  methods:{
    save(){
      boardList.push(this.newData);
      this.$router.push('/')
    }
  },
}
</script>

<style>

</style>