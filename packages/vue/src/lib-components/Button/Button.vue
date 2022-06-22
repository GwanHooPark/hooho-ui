<template>
  <button type="button" :class="classes" :style="style" @click.stop="btnClick()">{{ label }}</button>
</template>

<script>


export default {
  name: 'DadaButton',

  props: {
    label: {
      type: String,
      required: true,
    },
    primary: {
      type: Boolean,
      default: false,
    },
    size: {
      type: String,
      default: 'medium',
      validator: function (value) {
        return ['small', 'medium', 'large'].indexOf(value) !== -1;
      },
    },
    backgroundColor: {
      type: String,
    },
  },

  computed: {
    classes() {
      return {
        'dada-button': true,
        'dada-button--primary': this.primary,
        'dada-button--secondary': !this.primary,
        [`dada-button--${this.size}`]: true,
      };
    },
    style() {
      return {
        backgroundColor: this.backgroundColor,
      };
    },
  },

  methods: {
    btnClick() {
      this.$emit('click');
    },
  },
};
</script>
<style scoped>
   .dada-button {
    font-family: 'Nunito Sans', 'Helvetica Neue', Helvetica, Arial, sans-serif;
    font-weight: 700;
    border: 0;
    cursor: pointer;
    display: inline-block;
    line-height: 1;
  }
  .dada-button--primary {
    color: white;
    background-color: #1ea7fd;
  }
  .dada-button--secondary {
    color: #333;
    background-color: transparent;
    box-shadow: rgba(0, 0, 0, 0.15) 0px 0px 0px 1px inset;
  }
  .dada-button--small {
    font-size: 0.75rem;
    padding: 0 6px;
    border-radius:2px;
    height: 22px;
  }
  .dada-button--medium {
      font-size:0.9rem;
      padding:0 15px;
      border-radius:3px;
      height:34px;
  }
  .dada-button--large {
      font-size:1.1rem;
      padding:0 40px 0 40px;
      border-radius:5px;
      height:47px;
  }
</style>
