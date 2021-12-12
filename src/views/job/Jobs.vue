<template>
    <h1>Jobs</h1>
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
    
</template>

<script>
export default {
    data() {
        return {
            jobs: [
                { id: 1, title: "la mangue", description: "fruit tropical" },
                { id: 2, title: "la banane", description: "fruit tropical" },
                { id: 3, title: "l'orange", description: "fruit tropical" }
            ]
        }
    }

}
</script>

<style>

</style>