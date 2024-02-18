<template>
  <div>
    <h1>Moosavi</h1>
    <ul>
      <li v-for="(name, index) in names" :key="index">{{ name }}</li>
    </ul>
  </div>
  <!-- <Home :userInfo="userInfo" @childData="showData($event)"/> -->
  <!-- <Home>
    <template v-slot:ul>
      <ul>
      <li>Java</li>
      <li>Java Script</li>
    </ul>
    </template>
    <template v-slot:div>
      <div>
        <h1>mohamad</h1>
      </div>
    </template>
  </Home> -->
  <teleport to="#teleport-target">
    <Home/>
  </teleport>
</template>



<script>
import Home from './components/HomeWeb.vue'
export default {
  components: {
    Home
  },
  data(){
    return{
      // name: 'hasan',
      // lastname: 'moosavi',
      // age: 37
      userInfo: {
        name: 'hasan',
        lastname: 'moosavi',
        age: 37
      },
      names: ['hasan', 'mohamad', 'asiye', 'selin']
    };
  },
  methods: {
    showData(event) {
      console.log(event);
    }
  },
  provide: {
    user: 'hasan moosavi'
  }
};
</script>

<style>

</style>
