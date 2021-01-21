    <template lang="">
        <div class="row">
            <div class="col-md-4" v-for="course in courses" v-bind:key="course.id">
                <div class="card">
                    <img class="card-img-top" :src="course.image" :alt="course.title">
                    <div class="card-body">
                        <h4 class="card-title">{{ course.title }}</h4>
                        <p class="card-text"> lorem ipsum ... </p>
                    </div>
                </div>
            </div>
        </div>
    </template>

    <script>
    export default {
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
        
    }
    </script>

    <style lang="">
        
    </style>