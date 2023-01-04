<template>
    <div class="main">
        <Head>
            <Title>ABOUT</Title>
        </Head>
       <div class="firstsec" >
        <a href="mailto:mazen2m9@gmail.com">Contact</a>
        <P>All rights reserved Mazen 2022</P>
         </div>
        <div>
            <h1>ABOUT ME</h1>
        </div>
        <div></div>
        <div class="info">
            <div class="first">
                <p>Hello I am mazen emad im front-end developer and a student at arab academy for science and technology.</p>
            </div>
            <div class="second">
                <p>We aim to be the investors we wished we had when we started out. Lightning-fast, always on your side and fundamentally helpful.</p>
                <p>Our knowledge is your knowledge. Our network is your network. Your problems are our problems. We don't have all the answers, but we will help you find them.</p>
            </div>
        </div>
    </div>
</template>
<style >
@import url("https://fonts.googleapis.com/css2?family=Anton&family=Montserrat:wght@300;400&display=swap");
*{
    padding: 0;
    margin: 0;
    outline: 0vh;
}
.goback{
    color:rgb(141, 141, 141);
    text-decoration: none;
}
.main{
    background:  #000;
    font-family: "Montserrat", sans-serif;
    color:white;
    height: 100vh;
    }
    .firstsec{
        color:rgb(141, 141, 141);
    display: flex;
    justify-content: space-between;
    padding-top: 5%;
    margin-right: 3%;
    margin-left:6%;
    }
    .firstsec a{
        text-decoration: none;
        color:rgb(141, 141, 141);
    }
    h1{
    font-family: "Anton", sans-serif;
        font-size: 150px;
    margin-left:6%;
    }
    @media (max-width:450px){
        h1{
        font-size: 100px;
    } 
    }
    .second::before{
     content: '';
    width: 500px;
    border-top: solid 1px rgb(141, 141, 141);
    position: absolute;
    right: 5%;
    top: 0%;
    }
    .first::before{
    content: '';
    width: 300px;
    border-top: solid 1px rgb(141, 141, 141);
    position: absolute;
    left: 5%;
    top: 0%;
    }
    .info{
    background:  #000;
        position: relative;
        margin-top: 10%;
        color:#dfdfdf;
        display: flex;
        justify-content: space-between;
    }
  
    .first{
        margin-top: 20px;
        margin-left:5%;
        width: 300px;
    }
    .second{
        margin-top: 20px;
        width: 400px;
        margin-right:6%;
    }
    .second p{
        margin-bottom: 30px;
    }
</style>