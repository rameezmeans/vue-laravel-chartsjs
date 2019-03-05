<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                
                    <form @submit.prevent="createProduct">
                        <div class="form-group">
                            <label for="name">Name:</label>
                            <input type="text" class="form-control" id="name" v-model="product.name">
                        </div>
                        <div class="form-group">
                            <label for="pwd">Year:</label>
                            <input type="number" class="form-control" id="year" name="year" v-model="product.year">
                        </div>

                        <div class="form-group">
                            <label for="pwd">Price:</label>
                            <input type="number" class="form-control" id="price" name="price" v-model="product.price">
                        </div>

                        <button class="btn btn-success">Create Product</button>
                    </form>

            </div>
        </div>
    </div>
</template>

<script>
    export default {

        data(){

            return {

                product: {}
            }
        },

        mounted() {
            console.log('Product Component mounted.')
        },

        methods: {

            createProduct(){

                console.log(this.product);

                let uri = "http://charts_laravel.neura/products";

                axios.post(uri, this.product).then((response)=>{

                    window.location.reload();
                });
            }
        }
    }
</script>
