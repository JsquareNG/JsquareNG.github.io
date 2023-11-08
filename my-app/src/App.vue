<template>
  
  <div v-if="!isLoggedIn">
    <nav class="navbar navbar-expand-lg fixed-top shadow custom-navbar" id="nav_bar">
        <div class="container">
          <div class="navbar-header">
            <a class="navbar-brand" id="logo" href="/">
              <img src="./assets/bridgingdreamslogo.png" alt="bridgingDreamsLogo" width="75" height="60" style="outline: none;">
            </a>
          </div>
          <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
              <li class="nav-item">
                <router-link to="/" class="nav-link active font-weight-bold" aria-current="page"  style="font-size: 20px; color: #007bff; font-weight: bold;">Home</router-link>
              </li>
              <li class="nav-item">
                <router-link to="/login" class="nav-link font-weight-bold" aria-current="page"  style="font-size: 20px; color: #007bff; font-weight: bold">Login</router-link>
            </li>
          
            </ul>
          </div>
        </div>
    </nav>
  </div>
  <div v-else>
    <div v-if="type === 'tutor'">
        <nav class="navbar navbar-expand-lg fixed-top shadow custom-navbar" id="nav_bar">
            <div class="container container-fluid">
            <div class="navbar-header">
                <router-link to="/TutorHomePage" class="navbar-brand">
                <img src="./assets/bridgingdreamslogo.png" alt="bridgingDreamsLogo" width="75" height="60" style="outline: none;">
                </router-link>
            </div>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <router-link to="/TutorHomePage" class="nav-link active font-weight-bold" aria-current="page"  style="font-size: 20px; color: #007bff; font-weight: bold;">Home</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/library" class="nav-link font-weight-bold" aria-current="page"  style="font-size: 20px; color: #007bff; font-weight: bold">Resource Library</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/tutorprofile" class="nav-link font-weight-bold" aria-current="page" style="font-size: 20px; color: #007bff; font-weight: bold">Profile</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/myUploads" class="nav-link font-weight-bold" aria-current="page" style="font-size: 20px; color: #007bff; font-weight: bold">My Uploads</router-link>
                    </li>
                    <li class="nav-item">
                        <!-- <router-link to="/" class="nav-link font-weight-bold" aria-current="page"  style="font-size: 20px; color: #007bff; font-weight: bold">Sign Out</router-link> -->
                        <!-- <button @click="signOut()" class="nav-link font-weight-bold" style="font-size: 20px; color: #007bff; font-weight: bold" >Log Out</button> -->
                        <router-link to="/" class="nav-link font-weight-bold" aria-current="page" style="font-size: 20px; color: #007bff; font-weight: bold" @click="signOut">Log Out</router-link>

                    </li>
                </ul>
            </div>
            </div>
        </nav>
    </div>
    <div v-if="type === 'parent'">
        <nav class="navbar navbar-expand-lg fixed-top shadow custom-navbar" id="nav_bar">
            <div class="container container-fluid">
            <div class="navbar-header">
                <a class="navbar-brand" href="/home">
                <img src="./assets/bridgingdreamslogo.png" alt="bridgingDreamsLogo" width="75" height="60" style="outline: none;">
                </a>
            </div>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <router-link to="/home"  class="nav-link active font-weight-bold" aria-current="page"  style="font-size: 20px; color: #007bff; font-weight: bold;">Home</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/library" class="nav-link font-weight-bold" aria-current="page"  style="font-size: 20px; color: #007bff; font-weight: bold">Resource Library</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/parentProfile" class="nav-link font-weight-bold" aria-current="page" style="font-size: 20px; color: #007bff; font-weight: bold">Profile</router-link>
                    </li>
                    
                    <li class="nav-item">
                        <!-- <router-link to="/" class="nav-link font-weight-bold" aria-current="page"  style="font-size: 20px; color: #007bff; font-weight: bold">Sign Out</router-link> -->
                        <!-- <button @click="signOut()" class="nav-link font-weight-bold" style="font-size: 20px; color: #007bff; font-weight: bold" >Log Out</button> -->
                        <router-link to="/" class="nav-link font-weight-bold" aria-current="page" style="font-size: 20px; color: #007bff; font-weight: bold" @click="signOut">Log Out</router-link>
                    </li>
                </ul>
            </div>
            </div>
        </nav>
    </div>
  </div>
  <router-view/>
  <footer id="footer" class="bg-light text-center text-lg-start">
        <div class="container p-4">
            <div class="row">
                <div class="col-lg-3 col-md-6 mb-4 mb-md-0">
                    <h5 class="text-uppercase">Featured</h5>
                    <ul class="list-unstyled mb-0">
                        <li>
                            <text href="#" class="text-dark">Bridging Dreams Creators</text>
                        </li>
                        <li>
                            <text href="#" class="text-dark">Founded on 18th October 2023</text>
                        </li>
                        <li>
                            <text href="#" class="text-dark">Information System Students </text>
                        </li>
                        <li>
                            <text href="#" class="text-dark">Singapore Management Univeristy </text>
                        </li>
                    </ul>
                </div>
                <div class="col-lg-3 col-md-6 mb-4 mb-md-0">
                    <h5 class="text-uppercase mb-0">Follow Us</h5>
                
                    <ul class="list-unstyled" id="icon">
                        <li>
                            <i class='bx bxl-facebook' style="color: #0069d9"></i>
                            <i class='bx bxl-instagram' style="color: rgb(171, 57, 127)"></i>
                            <i class='bx bxl-twitter' style="color: #0069d9"></i>
                            <i class='bx bxl-youtube' style="color: #d9001d"></i>
                        </li>
                    </ul>
                </div>
                <div class="col-lg-3 col-md-6 mb-4 mb-md-0">
                    <h5 class="text-uppercase">Contact Us</h5>
                    <ul class="list-unstyled mb-0">
                        <li>
                            <i class='bx bxs-phone'></i>
                            <text href="#" class="text-dark">+65 94518710</text>
                        </li>
                        <li>
                            <i class='bx bxs-envelope' ></i>
                            <text href="#" class="text-dark">bridgingdreams@gmail.com</text>
                        </li>
                    </ul>
                </div>
                <div class="col-lg-3 col-md-6 mb-4 mb-md-0">
                    <h5 class="text-uppercase mb-0">Location</h5>
                    <ul class="list-unstyled">
                        <li>
                            <text href="#" class="text-dark">#09-08</text>
                        </li>
                        <li>
                            <text href="#" class="text-dark">Residences@Killiney</text>
                        </li>
                        <li>
                            <text href="#" class="text-dark">147 Killiney Road, S239566</text>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>
    <div class="custom-footer-margin">
        <div class="pt-2 pb-1 container text-center">
            <h6>Copyright &copy; 2023 Bridging Dreams</h6> 
        </div>
    </div>
    
</template>

<script>


import { auth } from './firebase/init.js'
import { signOut, onAuthStateChanged } from 'firebase/auth'

export default {
  data() {
    return {
      isLoggedIn: false,
      currentUser: null,
      type: ''
      
    }
  },
  methods: {
    signOut() {
      signOut(auth)
      .then(() => {
        // user signed-out
        this.isLoggedIn = false
        this.type = ''
        this.$router.push({name: "landingPage"})
      })
    },
    
  },
  mounted(){
    onAuthStateChanged(auth, (user) => {
      if (user) {
        // User is signed in
        this.type = user.displayName
        this.currentUser = user;
        this.isLoggedIn = true;
        
      } else {
        // User is signed out
        this.currentUser = null;
        this.type = ''
        this.isLoggedIn = false;
      }
    })
  }
}
</script>

<style>
    *{
      font-family: 'Constantia', serif;

    }
    #nav_bar {
        height: 76px;
        background-color: white;
        box-shadow: 0 0.5rem 1rem 0 rgba(0, 0, 0, 0.1);
    }

    /* .navbar-brand {
        margin-right: 20px;
    }

    .navbar-nav {
        margin-left: auto;
    } */

    .navbar-nav li {
    padding: 0 10px; /* Add padding to create a gap between nav items */
}
    .navbar-collapse {
        background-color: white;
        width: 100%;
        
    }

    @media (max-width: 991px) {
      .navbar-collapse {
        background-color: white;
        width: 100%;
        border-bottom: 2px solid lightgrey;
        border-left: 2px solid lightgrey;
        border-right: 2px solid lightgrey;   
      }
    }
 
    .navbar-nav li a {
        position: relative;
        text-decoration: none;
        padding: 6px 0;
    }

    .navbar-nav li a:before{
        content: '';
        height: 3px;
        width: 0%;
        background-color: #0D82FF;
        position: absolute;
        bottom: 0;
        left: 0;
        transition: all 0.4s ease;
    }

    .navbar-nav li a:hover:before{
        width: 100%;
    }


        .custom-footer-margin {
        background-color: black;
        color: white;
    }
</style>