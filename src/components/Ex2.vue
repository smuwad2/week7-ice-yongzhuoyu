<script>
import { addAbortListener } from 'events';

    export default { 
        // Add code in appropriate places
        data() {
            return {
                items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'],
                newItem: "",
            }
            
        },
        methods:{
            //remove the selected item in items array
            deleteItem(index){
                this.items.splice(index,1);
            },
            addItem(){
                //add new item into the items array 
                this.items.push(this.newItem);
            }
        }
    }
</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
    <ul>
        <li v-for="(item,index) in items" :key="index">
            {{ item }}
            <button @click="deleteItem(index)">
                Delete!
            </button>
        </li>
    </ul>

    <input type="text" v-model="newItem">
    <button @click="addItem">Add!</button>
</template>
