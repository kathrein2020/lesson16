<template>
  <div>
    <h1>lesson16</h1>

  <button @click="setSelectedComponent('active-goals')">Активные Цели</button>
  <button @click="setSelectedComponent('manage-goals')">Управление Целями</button>
  
  
  <!-- <keep-alive>    держать в ОЗУ памяти данные пока, данные не ичезают при переключении -->
    <keep-alive>
  <component :is="selectedComponent"></component>
  </keep-alive>

</div>
</template>

<script>
import ActiveGoals from './components/ActiveGoals.vue';
import ManageGoals from './components/ManageGoals.vue';


export default{
  components: {
    ActiveGoals,
    ManageGoals
  },
  data(){
    return {
      selectedComponent: 'active-goals'
    }
  },

  methods:{
    setSelectedComponent(name) {
      this.selectedComponent = name;
    }
  }
}
</script>

<style lang="scss">

// для transition    перехода глобально. в ActiveGoals

.v-enter-active,
.v-leave-active {
  transition: 0.8s ease;

}

.v-enter-from,
.v-leave-to{
  opacity: 0;


}


</style>
