<template>
    <h1>Jobs</h1>
    <div v-if="jobs.length">
        <table class="table">
            <thead>
                <tr style="background: red">
                    <th>Titre</th>
                    <th>Description</th>
                    <th>Action</th>
                </tr>
            </thead>
            <tbody>
                <div v-for="job in jobs" :key="job.id">
                    <tr>
                        <td>{{ job.title }}</td>
                        <td>{{ job.description }}</td>
                        <td>
                            <router-link :to="{ name: 'JobDetails', params: { id: job.id } }">
                                Détail
                            </router-link>
                        </td>
                    </tr>
                </div>
            </tbody>
        </table>
    </div>
    <div v-else>
        Jobs loading...
    </div>
    
    
</template>

<script>
export default {
    data() {
        return {
            jobs: []
        }
    },

    mounted() {
        fetch("http://localhost:3000/jobs")
        .then(response => {
            response.json().then(data => {
                this.jobs = data
            })
        })
        .catch(error => {
            console.log(error.message)
        })
    }

}
</script>

<style>

</style>