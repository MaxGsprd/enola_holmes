<template>
    <div>
        <div id="userInfo">
            <h1>{{user.firstname}} {{user.lastname}}</h1>
            <p><span class="field">gender: </span>{{user.gender}}</p>
            <p><span class="field">email: </span>{{user.email}}</p>
        </div>
        <Graphs v-bind:dataDates="dataDates" v-bind:dataVal="dataVal" v-bind:user="user"/>
    </div>
</template>

<script>
import Graphs from './Graphs.vue';

export default {
    name: 'GetUserData',
    components: {
        Graphs,
    },
    data() {
        return {
            data: [],
            user: [],
            dataDates: [],
            dataVal: []
        }
    },
    created () {
        var axios = require('axios');
        const url = "https://dev1-gojibrain.azurewebsites.net/testset";
        axios.get(url)

        .then(response => {
            this.user = response.data.user
            for (const dates of response.data.data) {
                this.dataDates.push(dates.date)
            }
            for (const val of response.data.data) {
            this.dataVal.push(val.value)
            }
        })
        .catch(error => console.log(error))
    },
}
</script>

<style scoped>

    #userInfo {
       margin-bottom: 20px;
       width: 100%;
       color:#fff;
       text-shadow: 2px 2px #444;
    }

    #userInfo p {
        padding: 10px 0;
        font-style: italic;
    }

    .field {
        font-weight: bold;
        font-style: normal;
    }
</style>