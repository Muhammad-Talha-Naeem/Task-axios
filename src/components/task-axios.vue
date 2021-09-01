<template>
    <div>
        <table>
            <tr v-for="product in products" v-bind:key="product.name">
                <td><img v-bind:src="product.imgUrl" width="200"  v-bind:alt="product.name"></td>
                <td>{{product.name}}</td>
                <td>{{product.price}}</td>
            </tr>
        </table>
    </div>
</template>
<script>
import Axios from "axios";
export default {
    name : "Task",
    data(){
        return{
            products:[],
        }
    },
    mounted(){
        Axios.get('http://localhost:3000/products')
        .then(resp=> this.products = resp.data);

    }
}
</script>
