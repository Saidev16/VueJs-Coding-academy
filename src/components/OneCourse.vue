<template lang="">
            <div class="card">
                <img class="card-img-top" :src="image" :alt="title">
                <div class="card-body">
                    <h4 class="card-title">{{ title }}</h4>
                        <p class="card-text"> lorem ipsum ... </p>
                        <button class="btn btn-sm btn-danger" @click="deleteOne(id)">Delete</button>

                </div>
            </div>
</template>
<script>
export default {
    props: ['id','title','image'],
    methods: {
        deleteOne(id){
            this.$emit('delete',id)
        }
    },

}
</script>
<style lang="">
    
</style>