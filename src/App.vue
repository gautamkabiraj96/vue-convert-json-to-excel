<template>
  <div id="app">
    <div @click="downloadFile()" class="np-btn">Export to excel</div>
    <div v-for="(investor, i) in investorsList" :key="i">
      <div class="np-list">
        {{ investor.id + 1 }}. {{ investor.name }}, {{ investor.email }},
        {{ investor.investment }}
      </div>
    </div>
  </div>
</template>

<script>
import exportFromJSON from "export-from-json";
export default {
  name: "App",
  methods: {
    downloadFile() {
      const data = this.investorsList;
      const fileName = "np-data";
      const exportType = exportFromJSON.types.csv;

      if (data) exportFromJSON({ data, fileName, exportType });
    },
  },
  data() {
    return {
      investorsList: [
        {
          id: 0,
          name: "Gautam",
          email: "gautam@example.com",
          investment: "Stocks",
        },
        {
          id: 1,
          name: "Sam",
          email: "sam@example.com",
          investment: "Bonds",
        },
        {
          id: 2,
          name: "Tim",
          email: "tim@example.com",
          investment: "Options",
        },
        {
          id: 3,
          name: "Kim",
          email: "kim@example.com",
          investment: "Stocks",
        },
        {
          id: 4,
          name: "John",
          email: "john@example.com",
          investment: "Options",
        },
        {
          id: 5,
          name: "Lee",
          email: "lee@example.com",
          investment: "Stocks",
        },
        {
          id: 6,
          name: "Charlotte",
          email: "charlotte@example.com",
          investment: "Options",
        },
        {
          id: 7,
          name: "Amy",
          email: "amy@example.com",
          investment: "Stocks",
        },
        {
          id: 8,
          name: "Mark",
          email: "mark@example.com",
          investment: "Bonds",
        },
        {
          id: 9,
          name: "Rose",
          email: "rose@example.com",
          investment: "Stocks",
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.np-list {
  padding: 2px 8px;
  margin: 12px 8px;
  border: 1px solid #107fda;
  background: #ffffff;
  border-radius: 6px;
  color: #107fda;
}
.np-btn {
  padding: 2px 8px;
  margin: 12px 8px;
  border: 1px solid #107fda;
  width: 110px;
  background: #107fda;
  border-radius: 6px;
  color: #ffffff;
  cursor: pointer;
}
</style>
