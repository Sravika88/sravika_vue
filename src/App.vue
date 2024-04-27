<template>
  <JobHeader/>
  <JobList :jobsList = jobsList />
</template>

<script>
import JobHeader from "./components/JobHeader.vue";
import JobList from "./components/JobList.vue";

  export default{
    name:"App",
    components:{
      JobHeader,
      JobList
    },
    data(){
      return {
        jobsList:[]
      }
    },methods:{
      async fetchJobDetails(){
        const res = await fetch("https://jobhive.onrender.com/api");
        const jobsData = await res.json();
        console.log(jobsData);
        return jobsData[0].jobs;
      }
    },
    async created(){
      this.jobsList = await this.fetchJobDetails();
    }
  }
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400..700;1,400..700&display=swap');

  *{
     font-family: "Lora", serif;
  }
</style>