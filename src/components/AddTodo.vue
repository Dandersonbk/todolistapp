<template>
    <div>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Add Task...">
            <input type="submit" value="Submit" class="waves-effect waves-light btn">

        </form>

    </div>
</template>

<script>
import uuid from 'uuid';
export default {
    name: "AddTodo",
    data() {
        return{
            title: ''
        }
    },
    methods: {
        addTodo(){

            const newTodo = {
                id: uuid.v4(),
                title: this.title,
                completed: false
            }
            //Send up to parent
            this.$emit('add-todo', newTodo);

            this.title ='';
        }
    }
    
}
</script>

<style scoped>
form{
    display: flex;
    margin:1%;
    color:black;
}
input[type="text"] {
    flex:10;
    padding: 5px;
    color:black;

}
input[type="submit"] {
    flex: 2;
    color:black;
}
::placeholder{
    color: black;
    font-size: larger;
}

</style>
