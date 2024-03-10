<template>
    <NavBar />
    <router-view></router-view>
  </template>
  
  <script>
  import NavBar from './components/NavBar.vue'
  import "bootstrap/dist/css/bootstrap.min.css"
  import "bootstrap/dist/js/bootstrap"
//   import $ from 'jquery';

export default {
components: {
    NavBar
},

// setup() {
//     $.ajax({
//     url: "http://127.0.0.1:3000/user/account/token/",
//     type: "post",
//     data: {
//         username: "aj",
//         password: "paj",
//         confirmedPassword: "paj",
//     },
//     success(resp) {
//         console.log(resp);
//     },
//     error(resp) {
//         console.log(resp);
//     }
//     });

//     $.ajax({
//     url:"http://127.0.0.1:3000/user/account/info/",
//     type:"get",
//     headers:{
//         Authorization:"Bearer "+"eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJiYTJmODJmNzllMTc0MjIyOGUxNzgzNWYwNjRmZmIyMSIsInN1YiI6IjEiLCJpc3MiOiJzZyIsImlhdCI6MTcwOTk4NzI0NSwiZXhwIjoxNzExMTk2ODQ1fQ.u-GWvCd7VreHUwTpfk7SSilVJlS9vi-ltZKh_3Y3Xek"
//     },
//     success(resp){
//         console.log(resp);
//     },
//     error(resp){
//         console.log(resp);
//     }
//     })

//     $.ajax({
//         url:"http://127.0.0.1:3000/user/account/register/",
//         type:"post",
//         data: {
//             username: "aj2",
//             password: "paj2",
//             confirmedPassword: "paj2",
//         },
//         success(resp){
//             console.log(resp);
//         },
//         error(resp){
//             console.log(resp);
//         }
//     });
// }

}
</script>

<style>
body {
background-image: url("@/assets/images/robot.jpg");
background-size: cover;
}
</style>
  