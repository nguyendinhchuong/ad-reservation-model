<template>
  <div id="app">
    <div class="container w-50" >
      <div class="left-side">
        <progress-bar
          :progresses="progresses"
          :isActive="isActive"
          @switch-tab="switchTab"
          :isLast="isLast"
        />
        <placement v-if="isActive===progresses[0]" @next="next" />
        <date v-if="isActive===progresses[1]" :dates="dates" @next="next" />
        <account v-if="isActive===progresses[2]" @next="next" />
        <creative v-if="isActive===progresses[3]" @next="next" />
        <payment v-if="isActive===progresses[4]" />
      </div>
      <!-- <div class="right-side" v-if="hasRightSide"></div> -->
    </div>
  </div>
</template>

<script>
import ProgressBar from "./components/Progress";
import Placement from "./components/Placement";
import Date from "./components/Date";
import Account from "./components/Account";
import Creative from "./components/Creative";
import Payment from "./components/Payment";

export default {
  name: "App",
  components: {
    ProgressBar,
    Placement,
    Date,
    Account,
    Creative,
    Payment
  },
  data() {
    return {
      progresses: [
        {
          name: "Placement",
          isPassed: true
        },
        {
          name: "Date",
          isPassed: false
        },
        {
          name: "Account",
          isPassed: false
        },
        {
          name: "Creative",
          isPassed: false
        },
        {
          name: "Payment",
          isPassed: false
        }
      ],
      isActive: {},
      isLast: {},
      dates: [
        {
          day: "12",
          month: "July",
          dayName: "Sunday"
        },
        {
          day: "13",
          month: "July",
          dayName: "Monday"
        },
        {
          day: "16",
          month: "July",
          dayName: "Wednesday"
        },
        {
          day: "4",
          month: "August",
          dayName: "Sunday"
        },
        {
          day: "7",
          month: "August",
          dayName: "Tuesday"
        }
      ]
    };
  },
  computed: {
    hasRightSide() {
      return (
        this.isActive === this.progresses[0] ||
        this.isActive === this.progresses[3]
      );
    }
  },
  created() {
    this.isActive = this.progresses[0];
    this.isLast = this.progresses[0];
  },
  methods: {
    next(tabName) {
      switch (tabName) {
        case "Placement":
          this.isActive = this.progresses[0];
          this.isLast = this.progresses[0];
          this.progresses[0].isPassed = true;
          break;
        case "Date":
          this.isActive = this.progresses[1];
          this.isLast = this.progresses[1];
          this.progresses[1].isPassed = true;
          break;
        case "Account":
          this.isActive = this.progresses[2];
          this.isLast = this.progresses[2];
          this.progresses[2].isPassed = true;
          break;
        case "Creative":
          this.isActive = this.progresses[3];
          this.isLast = this.progresses[3];
          this.progresses[3].isPassed = true;
          break;
        case "Payment":
          this.isActive = this.progresses[4];
          this.isLast = this.progresses[4];
          this.progresses[4].isPassed = true;
          break;
      }
    },
    switchTab(tabName) {
      switch (tabName) {
        case "Placement":
          this.isActive = this.progresses[0];
          break;
        case "Date":
          this.isActive = this.progresses[1];
          break;
        case "Account":
          this.isActive = this.progresses[2];
          break;
        case "Creative":
          this.isActive = this.progresses[3];
          break;
        case "Payment":
          this.isActive = this.progresses[4];
          break;
      }
    }
  }
};
</script>

<style lang='scss'>
body {
  margin: 0;
  padding: 0;
  background-color: #bed5fc;
}
button{
  cursor: pointer;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #0e1952;
}
.container {
  display: flex;
  margin: 2rem auto;
  background-color: #f9faff;
  border: none;
  border-radius: 0.5rem;
  height: 90vh;
}
.w-80 {
  width: 1130px;
}
.w-50 {
  width: 570px;
}
.left-side {
  padding: 2rem;
  width: 570px;
}
.right-side {
  width: 565px;
}
</style>
