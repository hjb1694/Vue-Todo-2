<template>
    <form class="addForm">
        <h2>Add Todo</h2>
        <input type="text" v-model="newItem"/>
        <button type="submit" @click.prevent="addNewItem">Add</button>
    </form>
</template>

<script>
export default {
    props : {
        addToDo : {
            type : Function
        }
    }, 
    data : function(){
        return {
            newItem : ''
        }
    }, 
    methods : {
        addNewItem : function(){

            if(this.newItem.length > 0){
            this.addToDo(this.newItem);
            this.newItem = '';
            }

        }
    }
}
</script>

<style scoped>
    .addForm{
        background:#fff;
        border:1px solid #ccc;
        border-radius:.5rem;
        padding:1rem;

    }

    input{
        font-size:1.6rem;
        border:1px solid #ccc;
        padding:1rem;
        display:block;
        width:100%;
        border-radius:.5rem;
        color:#555;
        outline:none;
        margin:1rem 0;
        
    }

    input:focus{
        border:1px solid #4182ab;
    }

    button{
        padding:.8rem 1rem;
        background:#4182ab;
        color:#fff;
        font-size:1.6rem;
        font-family:inherit;
        border:0;
        border-radius:.5rem;
        cursor:pointer;
        transition:background .5s;
        outline:none;
    }

    button:hover{
        background:#336787;
    }
</style>