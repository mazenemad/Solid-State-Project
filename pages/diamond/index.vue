<template>
    <div>
    <div class="canvas-wrapper">
        <canvas ref="webgl" id="atom" class="webgl"></canvas>
      </div>
      <button id="myImg"  class="button-74" role="button">Show Details</button>
           <img id="img" style="display:none;" src="~/assets/img/diamond.png" >

<!-- The Modal -->
<div id="myModal" class="modal">
  <span class="close">&times;</span>
  <img class="modal-content" src="" id="img01">
  <div id="caption"></div>
</div>
    </div>
    </template>
    <style scoped>
    
    *{
      overflow-x:hidden;
      padding: 0;
      margin: 0;
    }
    canvas{
      position:absolute;
      z-index: -1;
    }

    button{
      position:absolute;
      top:2%;
      right:2%;
    }
    
    .photo{
      /* background:white; */
      height: 100%;
      width: 400px;
      position:absolute;
      z-index: 100;
      right:2%;

    }
    #myImg {
  border-radius: 5px;
  cursor: pointer;
  transition: 0.3s;
}

#myImg:hover {opacity: 0.7;}

/* The Modal (background) */
.modal {
  display: none; /* Hidden by default */
  position: fixed; /* Stay in place */
  z-index: 1; /* Sit on top */
  padding-top: 100px; /* Location of the box */
  left: 0;
  top: 0;
  width: 100%; /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgb(0,0,0); /* Fallback color */
  background-color: rgba(0,0,0,0.9); /* Black w/ opacity */
}

/* Modal Content (image) */
.modal-content {
  margin: auto;
  display: block;
  width: 80%;
  max-width: 700px;
}

/* Caption of Modal Image */
#caption {
  margin: auto;
  display: block;
  width: 80%;
  max-width: 700px;
  text-align: center;
  color: #ccc;
  padding: 10px 0;
  height: 150px;
}

/* Add Animation */
.modal-content, #caption {  
  -webkit-animation-name: zoom;
  -webkit-animation-duration: 0.6s;
  animation-name: zoom;
  animation-duration: 0.6s;
}

@-webkit-keyframes zoom {
  from {-webkit-transform:scale(0)} 
  to {-webkit-transform:scale(1)}
}

@keyframes zoom {
  from {transform:scale(0)} 
  to {transform:scale(1)}
}

/* The Close Button */
.close {
  position: absolute;
  top: 15px;
  right: 35px;
  color: #f1f1f1;
  font-size: 40px;
  font-weight: bold;
  transition: 0.3s;
}

.close:hover,
.close:focus {
  color: #bbb;
  text-decoration: none;
  cursor: pointer;
}

/* 100% Image Width on Smaller Screens */
@media only screen and (max-width: 700px){
  .modal-content {
    width: 100%;
  }
}

/* CSS */
.button-74 {
  background-color: #fbeee0;
  border: 2px solid #422800;
  border-radius: 30px;
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
}

.button-74:hover {
  background-color: #fff;
}

.button-74:active {
  box-shadow: #422800 2px 2px 0 0;
  transform: translate(2px, 2px);
}

@media (min-width: 768px) {
  .button-74 {
    min-width: 120px;
    padding: 0 25px;
  }
}
    </style>
      <script setup>
      // const webgl = ref(null)
      
      import * as THREE from 'three'
      import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls.js'
      import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader.js'
      onMounted(() => {
      // const canvas = webgl.value
      const scene = new THREE.Scene()
      // const gui = new dat.GUI();
      const canvas = document.querySelector('canvas.webgl')
    
      const gltfLoader = new GLTFLoader()
    let obj;
      gltfLoader.load('/diamond.glb',(gltf)=>{
        obj=gltf.scene
        scene.add(obj)
        obj.position.y=-2;
      })
      
      /**
       * Sizes
       */
      const sizes = {
          width: window.innerWidth,
          height: window.innerHeight
      }
      
    //light
const pointLight = new THREE.DirectionalLight( 0xffffff, 0., 100 );
// const  pointLight2= new THREE.DirectionalLight( 0x0000ff, 0.5, 100 );
pointLight.position.set( 2, 7, 0 );
// pointLight2.position.set( -2, -7, 0 );
// scene.add( pointLight );
const amlight = new THREE.AmbientLight('white',0.0)
// scene.add(amlight)

    let settings = {
    frontLight: {
      color: new THREE.Color(0xbe7c7c),
      intensity: 8.6,
      distance: 26.9,
      penumbra: 0,
      x: 10,
      y: 14,
      z: 14
    },
    backLight: {
      color: new THREE.Color(0xc9f0f0),
      intensity: 8,
      distance: 23,
      penumbra: 0,
      x: -19,
      y: -5.3,
      z: 3
    }
  };
    let scrolly;
    window.addEventListener('scroll',()=>{
      scrolly=window.scrollY
    })
    
    
    
      window.addEventListener('resize', () =>
      {
          // Update sizes
          sizes.width = window.innerWidth
          sizes.height = window.innerHeight
      
          // Update camera
          camera.aspect = sizes.width / sizes.height
          camera.updateProjectionMatrix()
      
          // Update renderer
          renderer.setSize(sizes.width, sizes.height)
          renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2))
      })
      
      /**
       * Camera
       */
      // Base camera
      const camera = new THREE.PerspectiveCamera(75, sizes.width / sizes.height, 0.1, 100)
      camera.position.set(0, 0, 15)
      scene.add(camera)
      
      // Controls
      const controls = new OrbitControls(camera, canvas)
      controls.enableDamping = true
      
      /**
       * Renderer
       */
      const renderer = new THREE.WebGLRenderer({
          canvas: canvas,
          alpha:true
      })
      renderer.shadowMap.enabled = true
      renderer.shadowMap.type = THREE.PCFSoftShadowMap
      renderer.setSize(sizes.width, sizes.height)
      renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2))
      renderer.setClearColor(0x000000)
      
      /**
       * Animate
       */
      const clock = new THREE.Clock()
      
      const tick = () =>
      {
          const elapsedTime = clock.getElapsedTime()
      
          // Update control
          controls.update()
      
          // Render
          renderer.render(scene, camera)
      
          // Call tick again on the next frame
          window.requestAnimationFrame(tick)
      }
      
      tick()


        // Get the modal
        var modal = document.getElementById("myModal");

// Get the image and insert it inside the modal - use its "alt" text as a caption
var img = document.getElementById("myImg");
var modalImg = document.getElementById("img01");
var captionText = document.getElementById("caption");
var relimg = document.getElementById('img')
img.onclick = function(){
  modal.style.display = "block";
  modalImg.src = relimg.src;
  captionText.innerHTML = this.alt;
}

// Get the <span> element that closes the modal
var span = document.getElementsByClassName("close")[0];

// When the user clicks on <span> (x), close the modal
span.onclick = function() { 
  modal.style.display = "none";
}

      })




      definePageMeta({
        layout:'modelslayout'
      })
      </script>