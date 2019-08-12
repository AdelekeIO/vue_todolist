<template>
    <div>
        <form  >
            <input type="text" v-model="title" name="title" id="title" placeholder="Add Todo..">
            <input type="button" @click="addTodo" value="Submit"  class="btn">
        </form>
    </div>
</template>

<script>
// import  uuid  from "uuid";

export default {
    name: "AddTodo",
    data() {
        return {
            title : ''
        }
    },
    methods:{
        addTodo(){
            // console.log(123);
            
            const newTodo = {
                // id: uuid.v4(),
                title: this.title,
                completed: false

            }

            // Send up to parent
            this.$emit('add-todo', newTodo);

            this.title="";
        }
    }
}
</script>

<style scoped>
form{
    display: flex;
}

input[type="text"]{
    flex: 10;
    padding: 5px
}

</style>