<template>
    <div class="page">
    <header><h1>Vue Fire todo1</h1></header>
    <main>
      <div class="todos">
        <div class="write">
          <input type="text"/>
          <button class="btn add">Add</button>
        </div>
        <ul class="list">
          <li v-for="(todo,i) in todos" :key="i">
            <i class="far fa-check-square"></i>
            <span>
                <li>
                    <span>{{ todo.text }}</span>
                </li>
              <b>
                <a href="">Edit</a>
                <a href="">Del</a>
              </b>
            </span>
          </li>
        </ul>
      </div>
    </main>
    </div>
</template>

<script>
export default {
    data() {
        return {
        todos:[
        {text: '공부하기', state: 'yet'},
        {text: '운동하기', state: 'done'},
        {text: '글쓰기', state: 'done'},
      ]
        }
    },
    props: ['todoList'],
}
</script>

<style>