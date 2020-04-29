<template>
  <div class="flex flex-column flex-sp-btw calc-height">
    <div class="wrap">
      <div class="desc-header">Select Ad Placement</div>
      <div
        class="desc-content"
      >Choose an ad slot by selecting one of the options below. Use the interactive block on the right to see where the ad will display in the newsletter.</div>
      <div
        class="place-option"
        v-for="option in options"
        :key="option.id"
        @click="optionChoosing(option.id)"
      >
        <div class="option-desc">
          <i class="fas fa-check-circle" :class="isChoosed === option.id ? 'active': 'hidden'"></i>
          <div class="wrap">
            <div class="header" :class="{'active': isChoosed === option.id}">{{option.header}}</div>
            <div class="content">{{option.content}}</div>
          </div>
        </div>
        <div class="price-box">
          {{option.price}}
          <i class="fas fa-chevron-down"></i>
        </div>
      </div>
    </div>
    <button class="btn" @click="handleClick">
      Select Date &nbsp;
      <i class="fas fa-arrow-right"></i>
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      options: [
        {
          id: "1",
          header: "Main ad placement",
          content: "300 x 250 Banner at the top of email",
          price: "$130.00"
        },
        {
          id: "2",
          header: "Footer with banner",
          content: "150 x 100 Bottom right rectangle ad",
          price: "$70.50"
        }
      ],
      isChoosed: "1"
    };
  },
  methods: {
    handleClick() {
      this.$emit("next", "Date");
    },
    optionChoosing(id) {
      this.isChoosed = id;
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
.place-option {
  background-color: #fff;
  border: none;
  border-radius: 0.5rem;
  box-shadow: 1px 2px 3px #f4f5fa;
  display: flex;
  justify-content: space-between;
  padding: 1.5rem 1rem;
  margin-bottom: 1rem;
  & .active {
    color: #1062f5;
  }
  & .option-desc {
    display: flex;
    & .wrap {
      padding-left: 0.5rem;
      & .header {
        font-weight: 600;
      }
    }
    & .fa-check-circle {
      padding-top: 0.2rem;
    }
  }
  & .price-box {
    position: relative;
    padding: 0.3rem 0.8rem;
    background-color: #ecf2fe;
    border: none;
    border-radius: 5px;
    color: #1062f5;
    font-weight: 600;
    height: 1.3rem;
    & .fa-chevron-down {
      position: absolute;
      top: 2.5rem;
      color: #bcc2ce;
    }
  }
}
.btn {
  color: #fff;
  font-size: 1rem;
  border: none;
  border-radius: 5px;
  background-color: #1062f5;
  padding: 1rem;
}
.flex {
  display: flex;
}
.flex-column {
  flex-direction: column;
}
.flex-sp-btw {
  justify-content: space-between;
}
.calc-height {
  height: calc(90vh - 38px - 4rem);
}
.hidden {
  display: none;
}
</style>