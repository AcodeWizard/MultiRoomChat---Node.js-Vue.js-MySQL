<template>
    <div class="container">
        <div class="jumbotron mt-5">
            <div class="col-sm-8 mx-auto">
                <h1 class="text-center ">Chatroom</h1>
                <h3 class="text-center mt-5">Welcome to our fantastic chatroom!</h3>
                <h5 v-if="(auth==null || auth==undefined) && (token==null || token==undefined)"  class="text-center mt-3">Please login or sign up to start using</h5>
                <div v-if="(auth==null || auth==undefined) && (token==null || token==undefined)" class="jumbotron mt-5">
                    <div class="row">
                        <div class="col-md-6">
                            <router-link class="nav-link" to="/login"><button class="btn btn-lg btn-success btn-block">Login</button></router-link>
                        </div>
                        <div class="col-md-6">
                            <router-link class="nav-link" to="/register"><button class="btn btn-lg btn-primary btn-block">Regis</button></router-link>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import EventBus from './EventBus'

EventBus.$on('logged-in', test => {
    console.log(test)
})
export default {
    data () {
        return {
            auth: localStorage.auth,
            token: localStorage.usertoken
        }
    }
}
</script>
