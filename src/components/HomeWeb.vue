<template>
    <div>
        <!-- <h1>name: {{ userInfo.name }} </h1>
        <h1>lastname: {{ userInfo.lastname }} </h1>
        <h1>age: {{ userInfo.age }} </h1>

        <button @click="sendData">send data</button>

        {{ user }} -->
        <ul>
            <li v-for="(name, index) in names" :key="index">{{ name }}</li>
        </ul>
        <slot name="ul"></slot>
        <hr>
        <slot name="div"></slot>
    </div>
</template>

<script>
import {names} from '../mixin.js'
export default {
    // data() {
    //     return {
    //         name: 'moosavi'
    //     }
    // }

    // props: ['userName', 'userLastname', 'userAge']

    // props: {
    //     userName: String,
    //     userLastname: String,
    //     userAge: Number
    // }

    props: {
        userInfo: Object
    },
    mixins: [names],
    data() {
        return {
            data: 'DATA from child',
            // names: ['hasan', 'mohamad', 'asiye', 'selin']
        }
    },
    methods: {
        sendData(){
            this.$emit('childData', this.data);
        }
    },
    inject: ['user']
}
</script>

<style scoped>
div {
  color: red;
}
</style>