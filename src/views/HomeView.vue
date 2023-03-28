<template>
  <div class="HomeView">
    <img alt="Vue logo" src="../assets/logo.png">
    <div class="board-wrap">
      <div class="board-wrap__sort-area">
        <!-- todo -->
        <div class="board-wrap__sort-left"></div>
        <div class="board-wrap__sort-right">
          <button @click="$router.push('/create')">글쓰기</button>
        </div>
      </div>
      <div class="board-wrap__list-area">
        <table class="board-list">
          <colgroup>
            <col style="width:40px">
            <col style="width:80px">
            <col style="width:auto">
            <col style="width:100px">
            <col style="width:100px">
          </colgroup>
          <thead>
            <tr>
              <td v-for="item in ['No','분류','제목','작성자','작성일']" :key="item.index">
                {{item}}
              </td>
            </tr>
          </thead>
          <tbody>
            <tr v-for="board in boardList" :key="board.id" @click="goDetail(board.id)">
              <td>{{ board.id }}</td>
              <td>{{ board.field }}</td>
              <td>{{ board.title }}</td>
              <td>{{ board.writer }}</td>
              <td>{{ board.date }}</td>
            </tr>
          </tbody>
        </table>
      </div>
      <!-- todo -->
      <!-- <div class="pagination">
        <div class="pagination__controls">
          화살표 넣기
        </div>
        <ul class="pagination__pages">
          <li v-for=" i in 10" :key="i" class="pagination__page">{{ i }}</li>
        </ul>
      </div> -->
    </div>
  </div>
</template>

<script>

import boardList from '@/data/board'
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  // components: {
  //   HelloWorld
  // },
  data:()=> ({
    boardList
  }),
  methods:{
    goDetail(boardId){
      this.$router.push({
        name:'BoardDetail',
        params:{
          boardId,
        }
      })
    }
  }
}
</script>
<style scoped lang="scss">

.board-list {
  padding: 40px;
  width: 100%;
}
</style>
