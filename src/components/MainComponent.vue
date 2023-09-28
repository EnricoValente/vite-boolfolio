<script>
    import axios from 'axios';
	export default {
		data() {
			return {
				
                projects: []
			}
		},
        created() {
            axios.get('http://localhost:8000/api/projects')
                 .then(response=> {
                    console.log(response)
                    this.projects= response.data.projects.data;
                 });
        }
		
	}
</script>


<template>
    <main>
        <section>
            <div class="projects-container">
                <div v-for="project in projects" :key="project.id">
                    {{ project.title }}

                    <div>
                        {{ project.description }}
                    </div>

                    <div>
                        {{ project.chief }}
                    </div>

                    <div>
                        {{ project.start_date }}
                    </div>

                    <div>
                        {{ project.end_date }}
                    </div>
                </div>
            </div>
        </section>
    </main>
</template>

<style scoped>
   .projects-container {
    display: flex;
    flex-wrap: wrap;
   }

   .projects-container > * {
    width: calc(100% / 4);
    border: 1px solid blue;
    padding: 10px;
    text-align: center;
   }
</style>