<script>
export default {
    data(){
        const toggleStatus = () => {
            if (this.status === 'active') {
                this.status = 'pending';
            } else if (this.status === 'pending'){
                this.status = 'inactive';
            } else{
                this.status = 'active';
            }
        };

        return {
          name: 'John Doe',
          status: 'active',
          tasks: ['Task One', 'Task Two', 'Task Three'],
          toggleStatus,
          link: 'www.google.pt'

        };
    },

    methods:{
      toggleStatus() {
        if (this.status === 'active') {
            this.status = 'pending';
        } else if (this.status === 'pending'){
            this.status = 'inactive';
        } else{
            this.status = 'active';
        }
      }
    }

};


</script>

<template>
  <h1>{{name}}</h1>
  <p v-if="status==='active'">User is active</p>
  <p v-else-if="status==='pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <h3>Tasks:</h3>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>
  <!--<a v-bind:href="link">Click for Google</a>-->
  <a :href="link">Click for Google</a>

  <!--<button v-on:click="clickToggle"></button>-->
  <button @:click="toggleStatus">Change Status</button>
</template>
