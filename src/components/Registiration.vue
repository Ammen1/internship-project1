<template>
   <div style='background-color: blue;'>
       <div class="flex items-center justify-center h-screen">
           <div class="hidden sm:block  bg-cover h-full bg-blue">
               <div class="bg-blue-800 w-full h-screen bg-opacity-20">
               </div>
           </div>
           <div class="sm:w-1/2  hover:bg-blue-600 transition-colors">
               <div class="p-5 w-4/5 mx-auto text-left font-raleway" style="background-color: white; ">
                   <div class="text-center mb- w-13 h-6 font-bold border-radius-12 text-blue-800 border-orange-600  hover:bg-blue-400 transition-colors" >
                       <router-link to="/">
                            HOME
                       </router-link> 
                   </div>
                   <h1 class="font-bold text-left font-montserrat text-4xl sm:text-6xl mb-7">
                       Sign Up
                   </h1>
                   <p v-show="error" class="text-sm text-red-500">{{ errorMsg }}</p>
                   <form @submit="register">
                       <div class="my-4">
                           <h1 class="text-left font-bold mb-2 font-montserrat">Name</h1>
                           <input type="text" v-model="name" class="text-sm outline-none pb-2 w-4/5 bg-transparent border-b hover:border-blue-700 focus:border-blue-700">
                       </div>
                       <div class="my-4">
                           <h1 class="text-left font-bold mb-2 font-montserrat">Name</h1>
                           <input type="phone" v-model="phone" class="text-sm outline-none pb-2 w-4/5 bg-transparent border-b hover:border-blue-700 focus:border-blue-700">
                       </div>
                       <div class="my-4">
                           <h1 class="text-left font-bold mb-2 font-montserrat">Email</h1>
                           <input type="email" v-model="email" class="text-sm outline-none pb-2 w-4/5 bg-transparent border-b hover:border-blue-700 focus:border-blue-700">
                       </div>
                       <div class="my-4">
                           <h1 class="text-left font-bold mb-2 font-montserrat">Password</h1>
                           <input type="password" v-model="password" class="text-sm outline-none pb-2 w-4/5 bg-transparent border-b hover:border-blue-700 focus:border-blue-700">
                       </div>
                       <div class="my-4">
                           <h1 class="text-left font-bold mb-2 font-montserrat">Username</h1>
                           <input type="text" v-model="username" class="text-sm outline-none pb-2 w-4/5 bg-transparent border-b hover:border-blue-700 focus:border-blue-700">
                       </div>
                       
                       <button type="submit" :disabled="name.length < 4 || password.length < 8 || username.length < 3" class="bg-blue-700 p-5 text-white">
                           Sign Up 
                       </button>
                   </form>
               </div>
           </div>
       </div>
   </div>
</template>
<script>
   export default {
       name: 'RegisterPage',
       data() {
           return {
               name: '',
               email: '',
               password: '',
               username: '',
               error: false,
               errorMsg: `An Error occurred, please try again`
           }
       },
       methods: {
           async register(e) {
               try {
                   e.preventDefault()
                       await this.axios.post(`http://localhost:3000/api/auth/local/register`, {
                       name: this.name,
                       password: this.password,
                       email: this.email,
                       username: this.username
                   })
                   this.$router.push('login')
               } catch(e) {
                   this.error = true
                   this.email = ''
               } 
           }
       }
   }
</script>
<style scoped>
</style>