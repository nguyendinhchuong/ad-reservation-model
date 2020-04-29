<template>
  <div class="flex flex-column flex-sp-btw calc-height">
    <div class="wrap">
      <div class="flex flex-sp-btw flex-align-item-center mt-2">
        <div class="desc-header">Confirm Payment</div>
        <div class="flex flex-sp-btw">
          <div class="logo-item card-check">
            <i class="fas fa-money-check active"></i>
          </div>
          <div class="logo-item apple">
            <img src="https://cdn.iconscout.com/icon/free/png-256/apple-853-675472.png" alt />
          </div>
          <div class="logo-item google">
            <img
              src="https://cdn2.iconfinder.com/data/icons/social-icons-color/512/google-2-512.png"
              alt
            />
          </div>
        </div>
      </div>
      <div class="flex flex-align-item-center detail-box mt-1">
        <img src="/img/mess.png" alt />
        <div class="place-option">
          <div class="option-desc">
            <div class="wrap">
              <div class="header">Main ad placement</div>
              <div class="content">14th April, Sunday</div>
            </div>
          </div>
        </div>
        <div class="price-box">$70.50</div>
      </div>
    </div>
    <div class="card-info flex flex-column flex-sp-btw">
      <input class="input w-1" placeholder="Full Name" />
      <input class="input w-1" placeholder="Card Number" />
      <div class="flex flex-sp-btw">
        <div class="wrap">
          <div class="text">VALID THRU</div>
          <div class="flex">
            <input class="input w-3" placeholder="MM" />
            <input class="input w-3 ml-1" placeholder="YY" />
          </div>
        </div>
        <div class="wrap">
          <div class="text">CVC</div>
          <div class="flex">
            <input class="input w-3" placeholder="CVC" />
          </div>
        </div>
      </div>
    </div>
    <button class="btn btn-primary">Pay $58.00</button>
  </div>
</template>

<script>
export default {
  methods:{
    
  }
};
</script>

<style lang="scss" scoped>
.desc-header {
  font-size: 2rem;
}
.desc-content {
  color: #bcc2ce;
  margin-bottom: 2rem;
}

.active {
  color: #1062f5;
}
.logo-item {
  background-color: #fff;
  border: none;
  border-radius: 5px;
  box-shadow: 2px 3px 5px #f4f5fa;

  margin-left: 1rem;
  & img {
    width: 1.5rem;
    height: 1.5rem;
  }
}
.apple {
  padding: 0.3rem 0.5rem;
}
.card-check {
  padding: 0.5rem 0.65rem;
  box-shadow: 3px 3px 6px #c1cad8;
}
.google {
  padding: 0.3rem 0.5rem;
}
.w-2 {
  width: calc((570px - 7rem) / 2);
}
.w-1 {
  width: calc(570px - 10rem);
}
.w-3 {
  width: 3rem;
}
.mt-2 {
  margin-top: 2rem;
}
.mt-1 {
  margin-top: 1rem;
}
.ml-1 {
  margin-left: 1rem;
}
.wrap {
  position: relative;
  & .file-name {
    position: absolute;
    top: 0.4rem;
    left: 2rem;
    border: 1px dashed #1062f5;
    border-radius: 5px;
    color: #1062f5;
    padding: 0.5rem 1rem;
  }
}
.active {
  color: #1062f5;
}
.detail-box {
  background-color: transparent;
  border: 1px dashed #bcc2ce;
  border-radius: 3px;
  & img {
    width: 3rem;
    height: 3rem;
    padding: 0.8rem;
    border: none;
    border-radius: 1rem;
  }
  & .place-option {
    width: 68%;
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
.card-info {
  background-color: #fff;
  border: none;
  border-radius: 5px;
  padding: 2rem;
}
.input {
  border: 1px solid #eef4fe;
  border-radius: 3px;
  background-color: #f9faff;
  padding: 1rem;
  margin-bottom: 1rem;
  font-weight: 600;
  &::placeholder {
    color: #c1cad8;
  }
}
.input.w-3 {
  margin-bottom: 0;
}
.text {
  font-size: 0.8rem;
  color: #c1cad8;
  margin-bottom: 0.5rem;
}
.btn {
  font-size: 1rem;
  border: none;
  border-radius: 3px;
  padding: 1rem;
}
.btn-primary {
  background-color: #1062f5;
  color: #fff;
}
.btn-text {
  background-color: transparent;
  color: #1062f5;
  border: none;
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
.flex-align-item-center {
  align-items: center;
}
.calc-height {
  height: calc(90vh - 38px - 4rem);
}
</style>