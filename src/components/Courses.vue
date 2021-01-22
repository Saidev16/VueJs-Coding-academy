    <template lang="">
        <div class="row">
            <div class="col-md-4" v-for="course in courses" v-bind:key="course.id">

                <OneCourse :id='course.id' :title="course.title" :image="course.image" @delete="deleteOneCourse($event)" />

            </div>
        </div>
    </template>

    <script>    
    import OneCourse from './OneCourse';
    export default {
        components : {
            OneCourse
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
                ]
            }
        },
        methods: {
            deleteOneCourse(id){
                this.courses = this.courses.filter( course => course.id != id )
            }
        },
        
    }
    </script>

    <style lang="">
        
    </style>