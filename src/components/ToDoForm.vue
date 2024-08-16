
<script>
  export default {
    methods: {
        onSubmit() {
            if(this.label === "") {
                console.log("Label can't be null");
                return;
            }
        console.log('Label value: ', this.label);
        console.log('Name value: ', this.name);
        this.$emit('todo-added', this.label,this.name);
        this.label = "";
        },
    },
    data() {
        return {
        label:"",
        name:""
        };
    },
  };
</script>

<template>
  <form @submit.prevent="onSubmit">
    <label for="new-todo-input"> Label </label>
    <input
        type="text"
        id="new-todo-input-label"
        name="new-todo-input-name"
        autocomplete="off"
        v-model="label"
    />
    
    <label for="new-todo-input2"> Name </label>
    <input
        type="text"
        id="new-todo-input-name"
        name="new-todo-input-name"
        autocomplete="off"
        v-model="name"
    />
    <button type="submit">Add</button>
  </form>
</template>



