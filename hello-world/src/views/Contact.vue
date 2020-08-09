<template>
  <div>
    <input type="text" placeholder="Please enter your message" v-model="message" />
    <button type="button" @click="Submit()">Submit</button>
  </div>
</template>
<script>
export default {
  name: "Contact",
  data() {
    return {
      message: "",
    };
  },
  methods: {
    Submit() {
      if (this.message) {
        alert(this.message);
      }
    },
  },
};
</script>