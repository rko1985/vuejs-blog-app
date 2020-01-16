<template>
    <div class="row my-5">
        <div class="col-md-6 offset-3">
            <div class="card">
                <div class="card-body">
                    <h3 class="text-center my-4">Signup</h3>
                    <div class="form-group">
                        <input type="text" v-model="name" placeholder="Name" class="form-control">
                    </div>
                    <div class="form-group">
                        <input type="text" v-model="email" placeholder="Email" class="form-control">
                    </div>
                    <div class="form-group">
                        <input type="password" v-model="password" placeholder="Password" class="form-control">
                    </div>
                    <div class="form-group text-center">
                        <button @click="registerUser()" class="form-control btn btn-success">Signup</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    date(){
        return{
            name: '',
            email: '',
            password: ''
        }
    },

    methods: {
        registerUser(){
            /* eslint-disable no-console */
            console.log(this.name, this.email, this.password)
        }
    }
}
</script>