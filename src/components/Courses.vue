    <template lang="">

        <div class="row" v-if='state'>
            <div class="col-md-6 mx-auto">
                <AddCourse @cours="addOneCourse($event)" />
            </div>
        </div>
        
        
        <div class="row">
            <div class="col-md-6">
            <slot></slot>

                <h1>List of course</h1>
            </div>
            <div class="col-md-6 text-right" >
                    <button 
                    @click='changeState'
                    class= 'btn btn-sm'
                    :class=  "{  'btn-success': !state, 'btn-dark': state  }" >
                    {{ state ? 'Close' : 'New' }}
                    </button>
            </div>
        </div>
        
        <div class="row">
            <div class="col-md-4" v-for="course in courses" v-bind:key="course.id">

                <OneCourse :id='course.id' :title="course.title" :image="course.image" @delete="deleteOneCourse($event)" />

            </div>
        </div>
        
        <teleport to='#alert' v-if="courseDeleted" >
            <div class="alert alert-danger text-center">
                <strong>Course is deleted !</strong>
            </div>
        </teleport>

        <teleport to='#alert' v-if="courseAdded" >
            <div class="alert alert-success text-center">
                <strong>Course is Added !</strong>
            </div>
        </teleport>
    </template>

    <script>    
    import OneCourse from './OneCourse';
    import AddCourse from './AddCourse';
    export default {
        components : {
            OneCourse,
            AddCourse
        },
        data() {
            return {
                courses : [
                    {
                        'id':1,
                        'title': 'Learn ReactJS',
                        'image': 'https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/C2oT8I1eTXGg69ytJ69f'

                    },
                    {
                        'id':2,
                        'title': 'Learn Laravel',
                        'image':'https://www.jesusamieiro.com/wp-content/uploads/2019/10/Laravel.png'
                    },
                    {
                        'id':3,
                        'title': 'Learn VueJs',
                        'image':'https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/s3P1B6MDQlWUJhPhU7VC'
                    },{
                        'id':4,
                        'title': 'Learn Angular',
                        'image': 'https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/C2oT8I1eTXGg69ytJ69f'

                    },
                    {
                        'id':5,
                        'title': 'Learn PHP',
                        'image':'https://www.jesusamieiro.com/wp-content/uploads/2019/10/Laravel.png'
                    },
                    {
                        'id':6,
                        'title': 'Learn Javascript',
                        'image':'https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/s3P1B6MDQlWUJhPhU7VC'
                    }
                ],
                state : false,
                courseDeleted : false,
                courseAdded : false,
                   
            }            
             
        },
        

        methods: {
            deleteOneCourse(id){
                this.courses = this.courses.filter( course => course.id != id );
                this.courseDeleted = true;
                setTimeout( ()=> { this.courseDeleted = false; },3000 );
            } ,
            addOneCourse(course){
                this.courses.push(course)
                this.state = false;
                this.courseAdded = true ;
                setTimeout( ()=> { this.courseAdded = false; },3000 );
            },
            changeState(){
                this.state = !this.state;
            }

        },
        
    }
    </script>

    <style lang="">
        
    </style>