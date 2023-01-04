<template>
  <div class="">
  <Head>
          <Title>HOME</Title>
  </Head>

  <div class="body">

<section class="header">
<div class="container">
  <nav>
      <div class="logo"><h2>Solid State</h2></div>
      <div class="navbar">
          <ul>
              <li><a href="#"><NuxtLink to="/Start">START</NuxtLink></a></li>
              <li><a href="#"><NuxtLink to="/about">ABOUT</NuxtLink></a></li>
              <li><a href="#"><NuxtLink to="/feedback">FEEDBACK</NuxtLink></a></li>
          </ul>
      </div>
  </nav>

  <div class="hero">
      <div class="hero-content">
          <div class="hero-header">The website made to help students</div>
          <p class="hero-desc">
              This website helps you to understand and imagine some of the basic things in the subject, such as the shapes of crystals and their laws, to see them visually, so that it is easier to learn.                    </p>
          <button class="btn"><NuxtLink style="color:white" to="/Start">Start..</NuxtLink> </button>
      </div>
      <div class="hero-img">
      
      </div>
  </div>
</div>
</section>

<section class="about">
<div class="container padding-lr">
  <div class="about-header">
      <h1>About us</h1>
  </div>
  <div class="about-content">
      <div class="box">
          <div class="box-img"><img src="https://images.pexels.com/photos/574071/pexels-photo-574071.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" alt=""></div>
          <p style=" font-weight: bold; ">Mazen Emad</p>
          <p>Codding and Developing</p>
      </div>
      <div class="box">
          <div class="box-img"><img src="https://images.pexels.com/photos/1181244/pexels-photo-1181244.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" alt=""></div>
          <p style=" font-weight: bold; ">Yousof Amged</p>
          <p>Collecting information</p>
      </div>
      <div class="box">
          <div class="box-img"><img src="https://images.pexels.com/photos/196659/pexels-photo-196659.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" alt=""></div>
          <p style=" font-weight: bold; ">Moamen Zaher </p>
          <p>Collecting information</p>
      </div>
      <div class="box">
          <div class="box-img"><img src="https://images.pexels.com/photos/1181467/pexels-photo-1181467.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" alt=""></div>
          <p style=" font-weight: bold; ">Youana Samwel</p>
          <p>3D Models Design</p>
      </div>
  </div>
</div>
</section>

<section class="slogan">
<div class="container padding-lg">
  <div class="slogan-content">
      <p class="slogan-text">This website was made by more than one technology such as Threejs and Nuxtjs and it was developed by my-my</p>
  <span class="author">Under Supervision Of</span>
  <span class="author">Dr.Besher</span>
  <span class="author">Eng.Ahmed Abdelmoaty</span>
  </div>
</div>
</section>
</div >
</div>

</template>
<style>
@import url('https://fonts.googleapis.com/css2?family=Public+Sans:wght@300;400&display=swap');

* {
margin: 0;
padding: 0;
box-sizing: border-box;
outline: none;
text-decoration: none;
}

.body {
font-family: 'Public Sans', sans-serif;
}

.padding-lr {
padding: 40px 30px;
}

.padding-lg {
padding: 60px 40px;
}

.padding-tb {
padding: 50px 0;
}

.container {
max-width: 1024px;
margin: 0 auto;
}

.header {
background: #212121;
}

nav {
display: flex;
align-items: center;
justify-content: space-between;
padding: 20px 0;
}

nav .logo {
font-size: 25px;
color: #f9faf8;
}

nav .navbar ul {
display: flex;
list-style: none;
}

nav .navbar ul li {
margin-right: 15px;
}

nav .navbar ul li:last-child {
margin-right: 0;
}

nav .navbar ul li a {
text-decoration: none;
font-size: 18px;
color: #e5e7eb;
}

/** End Navbar **/

.hero {
padding: 100px 0;
display: flex;
align-items: center;
justify-content: space-between;
gap: 30px;
}

.hero .hero-content  {
flex: 1;
display: flex;
flex-direction: column;
align-items: flex-start;
}

.hero .hero-content .hero-header {
font-size: 48px;
font-weight: bold;
color: #f9faf8;
}

.hero .hero-content .hero-desc {
font-size: 20px;
color: #f9faf8;
margin: 15px 0;
}
@media (max-width:450px){
.hero .hero-content .hero-header {
width: 337px;
}
.hero{
  margin-left: 6%;
}
}
.hero .hero-img {
flex: 1;
}

.hero .hero-img img {
width: 100%;
}

.hero .hero-content .btn {
display: block;
padding: 10px 30px;
border-radius: 5px;
border: none;
background-color: #3882f6;
color: #f9faf8;
font-size: 18px;
font-weight: 300;
text-transform: uppercase;
}

/** End Hero **/

.about {
display: flex;
align-items: center;
flex-direction: column;
}

.about-header {
text-align: center;
margin-bottom: 30px;
font-size: 36px;
color: #212121;
text-transform: uppercase;
font-weight: bold;
}

.about-content {
display: flex;
align-items: center;
justify-content: space-between;
gap: 20px;
}
@media (max-width:440px) {
.about-content{
display: grid;
}
}

.about-content .box {
flex: 1;
text-align: center;
}

.about-content .box .box-img img {
width: 100%;
}

/** End About **/

.slogan {
background-color: #e5e7eb;
}

.slogan-content {
display: flex;
align-items: center;
justify-content: space-between;
flex-direction: column;
}

.slogan-content .slogan-text {
font-size: 30px;
font-weight: lighter;
font-style: italic;
color: #212121;
}

.slogan-content .author {
font-size: 18px;
font-weight: bold;
color: #212121;
align-self: flex-end;
}

.footer-wrapper {
display: flex;
align-items: center;
justify-content: space-around;
padding: 30px;
gap: 200px;
background-color: #3882f6;
border-radius: 5px;
}


</style>