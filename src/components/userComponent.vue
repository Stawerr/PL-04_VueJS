<template>
    <NameComponent :name=title ></NameComponent>
    <div class="grid-container">
        <ListUser  v-for="(user, i) of users" :user="user" :key="i" @click="sendName(user)"></ListUser>
    </div>
</template>

<script>
import axios from 'axios'
import ListUser from './listUser.vue';
import NameComponent from './nameComponent.vue';
    export default {
    data() {
        return {
            users: {},
            title:"",
        };
    },
    created() {
        this.loadUser();
    },
    methods: {
        loadUser() {
            axios
                .get("https://randomuser.me/api/?results=5")
                .then((response) => (this.users = response.data.results));
        },
        sendName(user){
            this.title=user.name.first
        }
    },
    components: { ListUser, NameComponent }
}
</script>

<style scoped>

.grid-container {
  display: grid;
  grid-template-columns: auto auto auto;
}

</style>