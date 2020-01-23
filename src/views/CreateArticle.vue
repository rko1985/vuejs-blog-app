<template>
    <div class="container">
        <div class="row">
            <div class="col-md-8 offset-md-2">
                <div class="card my-5">
                    <div class="card-body">
                        <picture-input 
                            accept="image/jpeg,image/png" 
                            size="5" 
                            button-class="btn btn-danger"
                            @change="onChange">
                        </picture-input>
                        <input type="text" placeholder="Title" class="form-control mb-3">
                        <wysiwyg v-model="content"/>
                        <div class="text-center">
                            <button @click="createArticle" class="btn btn-success btn-lg mt-3">Create Article</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import PictureInput from 'vue-picture-input';
import Axios from 'axios';

export default {
    components: {
        PictureInput
    },
    data(){
        return {
            content: '',
            image: null
        }
    },
    methods: {
        onChange(image){
            this.image = image;
        },
        createArticle(){
            const form = new FormData(); //vanilla JS function to create form data
            form.append('file', this.image);
            form.append('upload_preset', 'bh9lirrn');
            form.append('api_key', '579945137617826');

            Axios.post('https://api.cloudinary.com/v1_1/dtmdk5ve6/image/upload', form)
                .then(res => {
                    /* eslint-disable no-console*/
                    console.log(res)
                });
        }
    }
}
</script>