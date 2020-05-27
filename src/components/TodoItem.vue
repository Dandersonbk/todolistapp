<template>
    <div class = "todo-item " v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input style="visibility:visible;position: relative; left:0;" id="checkbox" for="todo" type="checkbox" v-on:change="markComplete">
            {{todo.title}}
            

        </p>
            <button @click="$emit('del-todo', todo.id)" class="btn-floating btn-small waves-effect waves-light red "><i class="material-icons">delete</i></button>


    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete(){
            this.todo.completed =!this.todo.completed;
        } 
    }
}
</script>

<style scoped>
.todo-item{
    display: flex;
    background: #f4f4f4;
    padding:1%;
    border-bottom: 1px #ccc dotted;
    margin: 1%;
    justify-content:space-between;

}
.todo-item p{
    padding-top:0.5%;
}
.is-complete {
  text-decoration: line-through;

}
button {
    float: right;
    cursor: pointer;
    
}

/* div p #checkbox{
    display: visible !important;
    position:relative !important;
    left: 0 !important;
    visibility: visible
}*/



</style>