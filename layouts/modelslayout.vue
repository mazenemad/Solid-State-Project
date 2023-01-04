<template >
    <div>
      <Head>
            <Title>MODELS</Title>
      </Head>
<div class="menu">
<div> <span ><NuxtLink v-on:click = "showMenu" class="button-74" role="button">Menu</NuxtLink></span></div>
</div>

<div v-on:click = "showMenu" class="fr" ref="fr"  id="fr">
<div> <span ><NuxtLink class="button-74" role="button" to="/fcc">FCC</NuxtLink></span></div>
<div><span ><NuxtLink class="button-74" role="button" to="/bcc">BCC</NuxtLink></span></div>
<div><span ><NuxtLink class="button-74" role="button" to="/nacl">Nacl</NuxtLink></span></div>
<div><span ><NuxtLink class="button-74" role="button" to="/sc">simple cube</NuxtLink></span></div>
<div><span ><NuxtLink class="button-74" role="button" to="/diamond">diamond</NuxtLink></span></div>
<div><span ><NuxtLink class="button-74 back" role="button" to="/Start">Go Back</NuxtLink></span></div>
       </div>
       <div class="by">
        <h2>Developed by Mazen Emad</h2>
       </div>
        <div>
        <slot />
    </div>
    </div>
   
</template>
<style scoped>
.menu{
  overflow:hidden;

    position: absolute;
    top:2%;
    z-index: 1;
}
.back{
    margin-top:10%;
}
.by{
    position: absolute;
    bottom: 3%;
    left:1%;
    color:white;
    font-size: 10px;
}
/* CSS */
.fr{
    display: none;
    position:absolute;
    top:15%;
}
.button-74 {
    background-color: #fbeee0;
  border: 2px solid #422800;
  border-radius: 5px;
  box-shadow: #422800 4px 4px 0 0;
  color: #422800;
  cursor: pointer;
  display: inline-block;
  font-weight: 600;
  font-size: 18px;
  padding: 0 18px;
  line-height: 50px;
  text-align: center;
  text-decoration: none;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  width: 150px;
}
.button-74:hover {
  background-color: #fff;
}
.button-74:active {
  box-shadow: #422800 2px 2px 0 0;
  transform: translate(2px, 2px);
}
@media (min-width: 450px) {
  .button-74 {
    min-width: 120px;
    padding: 0 25px;
  }
}
</style>
<script >

export default{
    methods:{
        showMenu(){
          this.s= this.$refs.fr
           if(this.s.style.display==='block'){
            this.s.style.display='none'
           }else{
            this.s.style.display='block'
           }
        }
     
    }
}
</script>