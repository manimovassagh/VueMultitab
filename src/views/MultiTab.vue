
<template>
  <div id="app">
    <v-card>
      <v-tabs v-model="tab">
        <v-tab v-for="n,index in length" :key="index" :to="routePathList[n - 1]">
          {{ routeList[n - 1] }}
          <v-btn
            v-show="n != 1"
            icon
            @click="length > 1 ? length-- : length == 1"
            align="center"
          >
            <v-icon size="10" v-show="n != 1"> mdi-close</v-icon>
          </v-btn>
        </v-tab>
        <v-btn icon @click="addTab">
          <v-icon size="15" align="center"> mdi-plus</v-icon>
        </v-btn>
      </v-tabs>
    </v-card>
    <router-link to="/home"
      ><v-btn>Click</v-btn></router-link
    >
  </div>
</template>

<script>
export default {
  data() {
    return {
      tab: 1,
      length: 1,
      path: this.$route.path,
      name: this.$route.name,
      routeList: ["Home"],
      routePathList: ["/home"],
    };
  },
  watch: {
    length(val) {
      this.tab = val - 1;
    },
      routePathList() {
      console.log("changed route")
    }
  },
  mounted() {
    console.log(this.routePathList);
    
  },
  methods: {
    addTab() {
      this.length++;
      this.routeList.push(this.$route.name);
      this.routePathList.push(this.$route.path);
    },
    pusher() {
      this.$router.push("/user");
    },
  }
};
</script>

<style scoped>

</style>

