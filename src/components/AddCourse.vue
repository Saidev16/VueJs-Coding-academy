<template lang="">
    <form @submit.prevent = "newCourse">
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
                    <option :value="myCategory.name"  v-for="myCategory in categories" :key="myCategory.id">
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
    
        <div class="my-3">
            <h5>Tags</h5>
            <div class="form-check">
              <label class="form-check-label mr-4" v-for="tag in tags" :key="tag" >
                <input type="checkbox" class="form-check-input" :value="tag" v-model="tagSelected" >
                    {{ tag }}
                    
              </label>
            </div>
        </div>
    
        
        <div>
            <button  class="btn btn-block btn-warning">Add course</button>
        </div>
    </form>


</template>

<script>
export default {
     data() {
         return {
             title : '',
             image : '',
             categories : [
                 { id:1, name: 'Frontend' },
                 { id:2, name: 'Backend' },
                 { id:3, name: 'Mobile' }
             ],
             category : '',
             typeOfPayment : 'paying',
             published : 'false',
             tags : ['framework','frontend','backend','javascript'],
             tagSelected : []
         }
     },
    methods: {
        newCourse(){
            let image = this.image;
            let title = this.title;
            let tag = this.tagSelected;
            let category = this.category;

            if(image=="" || title==""){
                return;
            }
            const course = {
                image,
                title,
                tag,
                category
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