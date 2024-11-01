<template>
<div>
  <!-- двойное обращение к классу -->
    <h1 class="heading" :class="classObject">Активные Цели</h1>
    <!-- :class="{'text-red': isTextActve}" -->

 <h2 :class="[heading2, blueClass]"> vvvvvvvvvvvvv </h2>
<h3 :style="{color: activecolor, fontSize: fontSize + 'px'}"> Transition123</h3>
    <Transition>
    <p v-if="isTextActve"> Lorem ipsum dolor sit amet, consectetur
         adipisicing elit. Dolore, amet eveniet fugit harum facilis id 
         excepturi necessitatibus assumenda mollitia deleniti? Nobis 
         necessitatibus, cupiditate deleniti veniam dolore corporis maxime error
          quia!</p> 
        </Transition>
          
          <br>
          <button @click="isTextActve =!isTextActve">Скрыть описание</button>


    </div> 
</template>

<script>
    export default{
  data(){
    return {
      isTextActve: true,

      headingClass: 'heading',
      redClass: 'text-red',
      blueClass: 'text-blue',
      heading2: 'heading2',

      fontSize: 40,
      activeColor: 'red'
    }
  },

computed: {
  classObject(){
    return {
      heading: this.isTextActve,
      'text-red': this.isTextActve
    }
  }
}

}
  </script>

<style lang="scss" scoped>
.heading {
   font-size: 40px;
   color: green;
}

.heading2 {
   font-size: 60px;
   color: rgb(197, 195, 73);
}

.text-red {
  color: red;
}

.text-blue {
  color: blue;
}
</style>