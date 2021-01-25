<template lang="">
    
    <div class="form-group ">
        <label for="title">title</label>
        <input v-model="title" id="title" type="text" class="form-control">
    </div>
    <div class="form-group">
        <label for="image">Image url</label>
        <input v-model="image" id="image" type="text" class="form-control">
    </div>

    <div class="form-group">
        <label for='category'>Category </label>
        <select v-model="category" id='category' class="form-control">           
                <option :value="index" v-for="(myCategory, index) in categories" :key="myCategory.id">
                    {{ myCategory.name }}
                </option>
        </select>
    </div>

    <div class="form-check form-check-inline my-3" >
        <label class="form-check-label">
            <input v-model="typeOfPayment" class="form-check-input" type="radio" name="typeOfPayment"  value="free"> Free
        </label >
        <label class="form-check-label ml-3" >
            <input v-model="typeOfPayment" class="form-check-input" type="radio" name="typeOfPayment"  value="paying" checked> Paying
        </label>
    </div>
    <div class="form-check">
      <label class="form-check-label">
        <input v-model="published" type="checkbox" class="form-check-input"  checked>
        Published
      </label>
    </div>

    
    <div>
        <button @click="newCourse" class="btn btn-block btn-warning">Add course</button>
    </div>

    <div id="well">
        title :  {{ title }}
        image :  {{ image }}
        category : {{ category }}
        type of payment : {{ typeOfPayment }}
        published : {{ published }}
     </div>
</template>

<script>
export default {
     data() {
         return {
             title : '',
             image : '',
             categories : [
                 { id:1, name: 'Frontend' },
                 { id:1, name: 'Backend' },
                 { id:1, name: 'Mobile' }
             ],
             category : '',
             typeOfPayment : 'paying',
             published : 'false'
         }
     },
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