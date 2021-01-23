<template lang="">
    
    <div class="form-group ">
        <label for="title">title</label>
        <input ref="title" id="title" type="text" class="form-control">
    </div>
    <div class="form-group">
        <label for="image">Image url</label>
        <input ref="image" id="image" type="text" class="form-control">
    </div>


    <div>
        <button @click="newCourse" class="btn btn-block btn-warning">Add course</button>
    </div>
</template>

<script>
export default {
    methods: {
        newCourse(){
            let image = this.$refs.image.value;
            let title = this.$refs.title.value;

            if(image=="" || title==""){
                return;
            }
            const course = {
                image,
                title
            }
            this.$emit('cours',course);

            this.$refs.image.value= "";
            this.$refs.title.value= "";

            

        }
    },
    
}
</script>
<style scoped>
    div{
        margin-bottom: 20px;
    }
</style>