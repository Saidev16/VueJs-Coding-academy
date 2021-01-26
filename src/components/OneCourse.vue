<template lang="">
            <div class="card">
                <img class="card-img-top" :src="image" :alt="title">
                <div class="card-body">
                    <h4 class="card-title">{{ title }}</h4>
                        <p class="card-text"> lorem ipsum ... </p>
                        <button class="btn btn-sm btn-danger" @click="deleteOne(id)">Delete</button>
                        <button class="btn btn-sm btn-dark ml-3" >{{category}}</button>
                        <hr>
                        <div v-for="oneTag in tag" :key="oneTag.id">
                            <a href="#" class="badge badge-primary">{{oneTag}}</a>
                     </div>
                </div>
            </div>
</template>
<script>
export default {
    props: ['id','title','image','category','tag'],
    methods: {
        deleteOne(id){
            this.$emit('delete',id)
        }
    },

}
</script>
<style lang="">
    
</style>