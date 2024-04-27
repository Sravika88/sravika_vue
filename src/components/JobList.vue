<template>
    <div>
        <div v-for="job of jobsList" :key=job.job_id>
            <JobDetails :job = job />
        </div>
    </div>
</template>

<script>
import JobDetails from "./JobDetails.vue";

    export default{
        name:"JobList",
        components:{
            JobDetails
        },
        props:{
            jobsList:Array
        }
    }
</script>

<style>
</style>