<template>
  <div class="flex flex-column flex-sp-btw calc-height">
    <div class="wrap">
      <div class="desc-header">Customize Ad Placement</div>
      <div
        class="desc-content"
      >Type in your ad details below and preview your ad using the interactive view to the right</div>
      <div class="flex flex-wrap flex-sp-btw">
        <div class="relative">
          <input class="input w-1" required />
          <span class="place-holder">Headline</span>
        </div>
        <div class="relative">
          <textarea class="input w-1" row="5" required />
          <span class="place-holder">Text</span>
        </div>
        <div class="relative">
          <input class="input w-1" required />
          <span class="place-holder">Link URL</span>
        </div>
        <div class="relative">
          <input class="input w-2" required />
          <span class="place-holder">CTA</span>
        </div>
        <div class="wrap">
          <input
            class="input-file w-2"
            ref="fileInput"
            type="file"
            placeholder="Choose file"
            @change="handleFileChange"
          />
          <div class="file-name" :class="{'border': fileName === 'Choose file'}">
            <i class="fas fa-paperclip" v-if="fileName!=='Choose file'"></i>
            &nbsp;&nbsp;{{fileName}}
          </div>
        </div>
      </div>
    </div>
    <button class="btn btn-primary" @click="handleClick($event)">
      Enter payment details
      <i class="fas fa-arrow-right"></i>
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      fileName: "Choose file"
    };
  },
  mounted() {},
  methods: {
    handleFileChange(e) {
      this.fileName = e.target.value.replace(/.*[/\\]/, "");
    },

    handleClick() {
      this.$emit("next", "Payment");
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
.input-file {
  padding: 1rem;
  margin-bottom: 1rem;
  font-weight: 600;
  background-color: transparent;
  opacity: 0;
}
textarea {
  resize: none;
}
.w-2 {
  width: calc((570px - 8rem) / 2);
}
.w-1 {
  width: calc(570px - 6rem);
}
.wrap {
  position: relative;
  & .file-name {
    position: absolute;
    top: 0.3rem;
    left: 2rem;
    
    color: #1062f5;
    padding: 0.5rem 1rem;
    pointer-events: none;
  }
  & .border {
    border: 1px dashed #1062f5;
    border-radius: 5px;
  }
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