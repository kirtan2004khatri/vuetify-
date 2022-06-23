<template>
  <h1>{{ title }}</h1>
  <!-- You can pass any reference to the element by writing ref -->
  <input type="text" ref="name">
  <button @click="clickHandler">Click me</button>
  <FirstCustom />
  <propCustom :propData="propdata" :condition="conditionData" @green="changer" />
  <slotCustom>

    <h1>This is the content passed in component tag</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Maxime blanditiis, omnis mollitia corporis natus,
      pariatur maiores quae officia repellendus corrupti ad repudiandae nesciunt dolor unde.</p>
    <!-- You can add slot with custom name using v-slot -->
    <template v-slot:links>
      <a href="">First link</a><br>
      <a href="#">Second link</a>
    </template>
  </slotCustom>
  <MyModal :modalTitle="mtitle" :modalContent="mcontent" :condition="change" v-if="showModal" @close="modalHandler"
    @changeColor="colorHandler()" />
  <button @Click="modalHandler">Modal</button>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import FirstCustom from './components/FirstCustom.vue'
import propCustom from './components/propCustom.vue'
import slotCustom from './components/slotCustom.vue'
import MyModal from './components/MyModal.vue'
export default {
  name: 'App',
  data() {
    return {
      title: "This is the title",
      propdata: "This is the data going into the prop",
      conditionData: 'red',
      mtitle: "This is the modal title",
      mcontent: "This is the content of the modal",
      showModal: false,
      change: "noraml"
    }
  },
  methods: {
    clickHandler() {
      // You can access the ref by $refs.name of the reference youi given
      console.log(this.$refs.name);
      this.$refs.name.innerHTML = "You clicked the button"
    },
    changer() {
      if (this.conditionData == 'green') this.conditionData = 'red'
      else this.conditionData = 'green'
    },
    modalHandler() {
      this.showModal = !this.showModal;
    },
    colorHandler() {
      if (this.change === "change") this.change = "normal"
      else this.change = "change"
    }
  },
  components: {
    FirstCustom, propCustom, slotCustom, MyModal
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
