<template>
  <div class="flex flex-column flex-sp-btw calc-height">
    <div class="wrap">
      <div class="desc-header">Sign In or Register Account</div>
      <div
        class="desc-content"
      >Create free account with Paved or sign in to finish booking ad placement.</div>
      <div class="flex flex-wrap flex-sp-btw">
        <div class="relative">
          <input class="input w-2" required />
          <span class="place-holder">First Name</span>
        </div>
        <div class="relative">
          <input class="input w-2" required />
          <span class="place-holder">Last Name</span>
        </div>
        <div class="relative">
          <input class="input w-1" required />
          <span class="place-holder">Email</span>
        </div>
        <div class="relative">
          <input class="input w-2" required />
          <span class="place-holder">Company Name</span>
        </div>
        <div class="relative">
          <input class="input w-2" required />
          <span class="place-holder">Website</span>
        </div>
        <div class="relative">
          <input class="input w-1" required />
          <span class="place-holder">Password</span>
        </div>
      </div>
      <button class="btn btn-text">Sign in to existing account</button>
    </div>
    <button class="btn btn-primary" @click="handleClick">
      Customize ad placement
      <i class="fas fa-arrow-right"></i>
    </button>
  </div>
</template>

<script>
export default {
  methods: {
    handleClick() {
      this.$emit("next", "Creative");
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

.active {
  color: #1062f5;
}
.input {
  border: none;
  border-radius: 3px;
  background-color: #fff;
  padding: 1rem;
  margin-bottom: 1rem;
  font-weight: 600;
  &::placeholder {
    color: #c1cad8;
  }
  &:focus ~ .place-holder,
  &:not(:focus):valid ~ .place-holder {
    top: 0.2rem;
    bottom: 10px;
    font-size: 11px;
    opacity: 1;
  }
}

.relative {
  position: relative;
}
.place-holder {
  position: absolute;
  font-weight: 600;
  font-size: 0.6875rem;
  color: #c1cad8;
  pointer-events: none;
  top: 1rem;
  left: 1rem;
  transition: 0.2s ease all;
}
.w-2 {
  width: calc((570px - 9rem) / 2);
}
.w-1 {
  width: calc(570px - 6rem);
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
.calc-height {
  height: calc(90vh - 38px - 4rem);
}
</style>