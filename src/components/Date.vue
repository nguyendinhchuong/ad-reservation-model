<template>
  <div class="flex flex-column flex-sp-btw calc-height">
    <div class="wrap">
      <div class="desc-header">Select Date</div>
      <div class="desc-content">Choose which date you want to book this ad on.</div>
      <div class="flex flex-wrap flex-sp-btw">
        <div v-for="(date, index) in filledDates" :key="index">
          
          <div class="date option-desc" :class="{'hidden': !date.day}">
            <div class="wrap">
              <div class="header">
                {{date.month}}&nbsp;
                <span class="active">{{date.day}}</span>
              </div>
              <div class="content">{{date.dayName}}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <button class="btn" @click="handleClick">
      Enter account details
      <i class="fas fa-arrow-right"></i>
    </button>
  </div>
</template>

<script>
export default {
  props: {
    dates: Array
  },
  computed: {
    filledDates() {
      const length = this.dates.length;
      let dates = [...this.dates];
      const placeHolderDate = {
        day: "",
        month: "",
        dayName: ""
      };
      const numPlaceHolder = length % 3 !== 0 ? 3 - (length % 3) : 0;
      for (let i = 0; i < numPlaceHolder; i++) {
        dates.push(placeHolderDate);
      }
      return dates;
    }
  },
  methods:{
    handleClick(){
      this.$emit('next', 'Account')
    }
  }
};
</script>

<style lang="scss" scoped>
.desc-header {
  font-size: 2rem;
  margin-top: 2.5rem;
  margin-bottom: 0.5rem;
}
.desc-content {
  color: #bcc2ce;
  margin-bottom: 2rem;
}
.date {
  width: calc((570px - 12rem) / 3);
  box-shadow: 1px 2px 3px #f4f5fa;
  background-color: #fff;
  border: none;
  border-radius: 0.5rem;
  padding: 1rem 1rem;
  margin-bottom: 1rem;
}
.active {
  color: #1062f5;
}
.option-desc {
  display: flex;
  & .wrap {
    padding-left: 0.5rem;
    & .header {
      font-weight: 600;
    }
  }
}
.btn {
  color: #fff;
  font-size: 1rem;
  border: none;
  border-radius: 3px;
  background-color: #1062f5;
  padding: 1rem;
}
.flex {
  display: flex;
}
.flex-column {
  flex-direction: column;
}
.flex-wrap {
  flex-wrap: wrap;
}
.hidden {
  visibility: hidden;
}
.flex-sp-btw {
  justify-content: space-between;
}
.calc-height {
  height: calc(90vh - 38px - 4rem);
}
</style>