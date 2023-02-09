<template>
    <div class="page">
<header><h1>Vue Fire todo1</h1></header>
<main>
  <div class="todos">
    <div class="write">
      <input type="text" v-model="addItemText" @keyup.enter="addItem"/>
      <button class="btn add" @click="addItem">Add</button>
    </div>
    <ul class="list">
      <li v-for="(item, i) in todos" :key="i" >
        <i
        @click="checkItem"
        :class="[item.state === 'yet' ? 'far' : 'fas', 'fa-check-square']">
        </i>
        <span>
            {{ item.text }}
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
        addItemText:'',
        todos:[
            {text: '공부하기', state: 'yet'},
            {text: '운동하기', state: 'done'},
            {text: '글쓰기', state: 'done'},
        ]
    }
},
props: ['todoData'],
methods: {
    addItem() {
        if (this.addItemText === '') return;
        this.todo.push({text: this.addItemText, state: 'yet'}),
        this.addItemText='';
    },
    checkItem(index) {
      this.item.state === 'yet' ? 'done far': 'yet fas fa-check-square'
    }
},
mounted() {
    this.$refs.writeArea.focus();   // writeArea는 뭐지??? 그리고 왜 $refs씀?? writearea는 자식 컴포넌트에 있는거 아닌가.. 
}
}
</script>

<style>
</style>