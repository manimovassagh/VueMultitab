
<template>
  <v-card>
    <v-tabs v-model="tab">
      <v-tab v-for="n in length" :key="n">
        Item {{ n }}
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
</template>

<script>
export default {
  data: () => ({
    length: 3,
    tab: null,
    routeList:["Default Tab"],
      routePathList:[],
  }),

  watch: {
    length(val) {
      this.tab = val - 1;
    },
  },

  methods: {
    addTab() {
      this.length++;
      this.routeList.push(this.$route.name);
      this.routePathList.push(this.$route.path);
    },
  },
};
</script>