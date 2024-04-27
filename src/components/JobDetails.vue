<template>
    <div class="job-container">
        <div class="job-details">
            <div class="job-image">
                <img :src=job.job_companyLogo alt=job.job_companyName class="image"/>
            </div>
            <div class="company-details">
                <h3>{{job.job_name}}</h3>
                <p>{{job.job_companyName}}</p>
            </div>
        </div>
            <p>{{job.job_description}}</p>
            <p><img src="https://img.icons8.com/?size=20&id=85149&format=png" alt="location icon" id="location"/>{{job.job_location}}</p>
            <p><b>{{job.job_salary}}</b></p>
            <h4>Requirements:</h4>
            <ul>
                <div v-for="requirement of job.job_requirements" :key=requirement>
                    <li>{{requirement}}</li>
                </div>
            </ul>
    </div>
</template>

<script>
    export default{
        name:"JobDetails",
        props:{
            job:Object
        }
    }
</script>

<style>
    .job-container{
        width:80%;
        margin:auto;
        border:transparent;
        border-radius: 10px;
        box-shadow:0 4px 8px 0 rgba(0,0,0,0.2),0 6px 20px 0 rgba(0,0,0,0.19);
        padding:1em;
        margin-bottom: 1em;
    }
    .job-details{
        display:flex;
        justify-content: left;
        align-items:center;
    }
    .company-details{
        margin-left: 3em;
    }
    .job-image .image{
        width:70px;
        height:70px;
    }
    #location{
       margin-right: 0.4em;
       vertical-align:middle;
    }
</style>