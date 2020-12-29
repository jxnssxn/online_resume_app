<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <p><h1>My name</h1></p>
    <h1>Summary/Bio</h1>
    <p><h1><img src= "https://fashionjournal.com.au/wp-content/uploads/2018/01/Grumpy-Cat-Portrait.jpg"></h1></p>
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function () {
    return {
      message: "Online Resume App",
    };
  },
  created: function () {},
  methods: {
    showResume: function (theResume) {
      console.log(theResume);
      this.currentResume = theResume;
      console.log("user's resume");
      document.querySelector("#resume-details").showModal();
    },
  },
};
</script>
