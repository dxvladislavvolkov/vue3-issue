<template>
 <button @click="onClick">{{text}}</button>
</template>

<script>

const baseComponent = {
  data() {
    const h = { d: 1 };
    return{
      a: h
    }
  },
  updated() {
    console.log(this.a.d)
  },
  provide() {
      return {
        a: this.a
      }
  },
};

export default {
  name: 'HelloWorld',
  extends: baseComponent,
  data() {
    return{
      text: "text"
    }
  },

  methods: {
    onClick() {
      this.text = "text2";
    }
  }
}
</script>
