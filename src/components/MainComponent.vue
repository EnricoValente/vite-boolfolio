<script>
    import axios from 'axios';
	export default {
		data() {
			return {
				title:'Main'
			}
		},
        created() {
            axios.get('http://localhost:8000/api/projects')
                 .then(response=> {
                    console.log(response)
                 });
        }
		
	}
</script>


<template>
    <div>
        <h2>
            {{ title }}
        </h2>
    </div>
</template>

<style scoped>
    h2 {
        color: greenyellow;
    }
</style>