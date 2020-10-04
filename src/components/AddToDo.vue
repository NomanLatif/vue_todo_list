<template>
    <div>
        <form @submit="addToDo">
            <input type="text" v-model="title" name="title" placeholder="Add todo...">
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>    
</template>

<script>
import { v4 as uuid } from "uuid";
export default {
    name: "AddToDo",
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addToDo(e) {
            e.preventDefault();
            const newToDo = {
                id: uuid(),
                title: this.title,
                completed: false
            }

            // send to parent
            this.$emit('add-todo', newToDo);
        }
    }
}
</script>

<style scoped>
 form {
    display: flex;
  }
  input[type="text"] {
    flex: 10;
    padding: 5px;
  }
  input[type="submit"] {
    flex: 2;
  }
</style>