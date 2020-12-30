<template>
  <div class="w3-container">
  <div class="home">
    <h1>{{ message }}</h1>
    <!-- <button v-on:click="studentIndex()">Get Recipes</button> -->
    <div v-for="student in students">
      <h1>{{ student.first_name }}</h1>
      <!-- <p><h1>My name</h1> -->
    </div>


    <div id="carouselExampleIndicators" class="carousel slide" data-bs-ride="carousel">
  <ol class="carousel-indicators">
    <li data-bs-target="#carouselExampleIndicators" data-bs-slide-to="0" class="active"></li>
    <li data-bs-target="#carouselExampleIndicators" data-bs-slide-to="1"></li>
  </ol>
  <div class="carousel-inner">
    <div class="carousel-item active">
      <!-- get all students to display in carousel -->
      <!-- first student -->
      <button v-on:click="showResume(resume)"><img src="https://image.shutterstock.com/image-photo/closeup-portrait-young-professional-beautiful-260nw-220418767.jpg" class="d-block w-75" alt="https://fashionjournal.com.au/wp-content/uploads/2018/01/Grumpy-Cat-Portrait.jpg"></button>
    </div>
      <!-- second student -->
    <div class="carousel-item">
      <button v-on:click="showResume(resume)"><img src="https://i.pinimg.com/originals/77/71/68/7771683223d86b237a3304d6f32828b9.jpg" class="d-block w-75" alt="https://fashionjournal.com.au/wp-content/uploads/2018/01/Grumpy-Cat-Portrait.jpg"></button>
    </div>
      <!-- third student -->
  </div>
  <a class="carousel-control-prev" href="#carouselExampleIndicators" role="button" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleIndicators" role="button" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </a>
    </div>


  </div>

  <!-- <p>
    First Name - first_name
    Last Name - last_name
    Email - email
    Phone Number - phone_number
    Short Bio - short_bio
    LinkedIn URL - linkedin_url
    Twitter Handle - twitter_handle
    Personal Blog/Website URL - personal_blog_url
    Online Resume URL - resume_url
    Github URL - githhub_url
    Photo - photo
  <br>
  <br>
    Experience
    Start Date - start_date
    End Date - end_date
    Job Title - job_title
    Company Name - company_name
    Details (one long text field) - details
  <br>
  <br>
    Details (one long text field) - details
    Skills
    Skill Name (E.g. Ruby, HTML, CSS) - skill_name
    Capstone
    Name - name
    Description - description
    URL - url
    Screenshot (Optional)
  </p> -->

    <!-- <h1>Summary/Bio</h1> -->
    <!-- <p><h1><img src= "https://fashionjournal.com.au/wp-content/uploads/2018/01/Grumpy-Cat-Portrait.jpg"></h1></p> -->
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      students: [],
      message: "Online Resume App",
    };
  },
  created: function () {
    this.indexStudent();
  },
  methods: {
    indexStudent: function () {
      console.log("resume index");
      axios.get("/api/students").then((response) => {
        console.log(response.data);
        this.students = response.data;
      });
    },
    // showResume: function (theResume) {
    //   console.log(theResume);
    //   this.currentResume = theResume;
    //   console.log("user'sresume");
    //   document.querySelector("#resume-details").showModal();
    // },
  },
};
</script>
