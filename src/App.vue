<template>
  <div>
    <the-header></the-header>
    <button @click="setSelectedComponent('active-goals')">Active Goals</button>
    <button @click="setSelectedComponent('manage-goals')">Manage Goals</button>
    <keep-alive>
      <component :is="selectedComponent"></component>
    </keep-alive>
    <!-- <badge-list></badge-list>
    <user-info
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    ></user-info>
    <course-goals>
      <template #default="goalProps">
        <h2>{{ goalProps.item }}</h2> 
      </template>
    </course-goals> -->
  </div>

</template>

<script>
import TheHeader from './components/TheHeader.vue';
import ManageGoals from './components/ManageGoals';
import ActiveGoals from './components/ActiveGoals.vue';
// import UserInfo from './components/UserInfo.vue';
// import BadgeList from './components/BadgeList.vue';
// import CourseGoals from './components/CourseGoals.vue';

export default {
  components:{
    TheHeader,
    ManageGoals,
    ActiveGoals
    // UserInfo,
    // BadgeList,
    // CourseGoals
  },
  data() {
    return {
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
      selectedComponent: 'active-goals'
    };
  },
  methods:{
    setSelectedComponent(component){  
        this.selectedComponent = component;
    }
  }
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>