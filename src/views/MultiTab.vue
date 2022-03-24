
<template>
  <div id="app">
  <v-app id="inspire">
    <v-card>
      <v-tabs v-model="tab"  >
        <v-tab  v-for="n in length" :key="n" :to="path">
          Item {{ n}}
          <v-btn icon @click="length>1?length--:length==1" align="center">
            <v-icon size="10" v-if="n!=1"> mdi-close</v-icon>
          </v-btn>
        </v-tab>
        <v-btn icon @click="addTab">
          <v-icon size="15" align="center"> mdi-plus</v-icon>
        </v-btn>
      </v-tabs>

    </v-card>
  </v-app>
</div>
</template>

<script>
export default {
  data() {
    return {
      tab: 1,
      length: 1,
      path:this.$route.path,
      name:this.$route.name,
      routeList:[]
    }
  },
watch: {
  length(val) {
    this.tab = val - 1
  }
},
mounted(){

  console.log(this.routeList)
},
methods: {
  addTab() {
    this.length++
    this.routeList.push(this.$route.path)
  },
}
}
</script>

<style>

</style>

