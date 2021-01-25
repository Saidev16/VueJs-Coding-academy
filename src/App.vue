<template>

  <Header />
  <div class="container" >
    <div class="row">
      <div class="col-md-6 mx-auto text-center" >

          <AddCourse />
          
      </div>
    </div>
    <Courses>
      <nav aria-label="breadcrumb">
         <ol class="breadcrumb">
           <li class="breadcrumb-item"><a href="#">Home</a></li>
           <li class="breadcrumb-item active" aria-current="page">List of courses</li>
         </ol>
      </nav>      

    </Courses>

  </div>
  <Footer url="https://udemy.com" title='Best Learning platforme' text='Learn latest technologies now' />  

</template>

<script>

import Header from './components/Header';
import Courses from './components/Courses';
import Footer from './components/Footer';
export default {
  name: 'App',
  components: {
    Header,
    Courses,
    Footer
  },
  data() {
    return {
      message : 'bright coding',
      state : false ,
      activeColor: ''

    }
  },
  methods: {
    handleClick(){
      console.log(this.$refs.book.value);
      this.$refs.book.classList.add('active');
      this.$refs.book.focus();

    },
    
  }
}
</script>

<style>
  .container{
    margin-top: 60px;
  }

</style>
