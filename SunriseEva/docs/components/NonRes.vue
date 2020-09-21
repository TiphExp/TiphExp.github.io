<template>
  <div class="bg">
    <article>
      <main>
        <div id="rain-container"></div>

<!--         <kinesis-container>
          <kinesis-element :strength="30">
            <div class="layer8 child">
              <img class="img-anime" src="../assets/images/parallax8.png" alt="" >  
            </div>
          </kinesis-element>

          <kinesis-element :strength="30" type="rotate">
            <div class="layer9 child">
              <img class="img-anime" src="../assets/images/parallax9.png" alt="" >  
            </div>
          </kinesis-element>
        </kinesis-container> -->
      </main>
      <footer>


        <div class="container_row parent">
          <div class="layer1 child">
            <img ref="l1image" class="l1image" src="../assets/images/parallax00.png" alt="" >  
          </div>

          <div class="layer5 child">
            <img ref="l5image" class="l5image" src="../assets/images/parallax5'.png" alt="" >  
          </div>

          <div class="layer3 child">
            <img class="img-anime" src="../assets/images/parallax3.png" alt="" >  
          </div>

          <div class="layer12 child">
            <img ref="l12image" class="l12image" src="../assets/images/parallax12.png" alt="" >
          </div>

          <div class="layer11 child">
            <img ref="l11image" class="l11image" src="../assets/images/parallax11.png" alt="" >  
          </div>

          <div class="layer4 child">
            <img ref="l4image" class="l4image" src="../assets/images/parallax4'.png" alt="">  
          </div>

          <div class="layer10 child">
            <img ref="l10image" class="l10image" src="../assets/images/parallax10.png" alt="" >  
          </div>

          <div class="layer2 child">
            <img class="img-anime" src="../assets/images/parallax2'.png" alt="" >  
          </div>
        </div>
      </footer>
    </article>
  </div>
</template>

<script>
  import { TimelineMax, TweenMax, Linear } from "gsap"
// import { TimelineMax} from "gsap"
export default { 

  data() {
    return {
      timeline: null
    };
  },

  mounted() {
var l5image = '.l5image';
var l4image = '.l4image';
var l11image = '.l11image';
var l12image = '.l12image';

// Rocks moving
new TimelineMax({ repeat: -1 })
  .to(l4image, 4, { x: 5 })
  .to(l4image, 4, { x: 0 })
  // Rei's face
new TimelineMax({ repeat: -1 })
  .to(l5image, 5, { y: 30 })
  .to(l5image, 5, { y: 0 })
// thick fog
  new TimelineMax({ repeat: -1 })
  .to(l11image, 3.75, { x: 20 })
  .to(l11image, 3.75, { x: 0 })
  // large fog
  new TimelineMax({ repeat: -1 })
  .to(l12image, 3.70, { y: 20 })
  .to(l12image, 3.70, { y: 0 })

var dropletQuantity = 50;

for (var i = dropletQuantity - 1; i >= 0; i--) {
  
  var pos = Math.floor((Math.random() * 100) + 1);
  var delay = Math.random();
  var speed = (Math.random() * 0.5) + 1.7;
  
  var droplet = document.createElement("div");
  // droplet.className = "droplet";
  droplet.classList.add("dropletclass");
  droplet.style.position = "absolute";
  droplet.style.left = pos + "%";
  droplet.style.top = 6 + "%";
  droplet.style.height = 40 + "px";
  droplet.style.width = 1 + "px";
  // droplet.style.transform = "rotate(30deg)";
  droplet.style.backgroundColor = "white";
  droplet.style.zIndex = pos + "%";
  
  TweenMax.to(droplet, speed, { y :1520, delay : delay, repeat:-1,ease:Linear.easeNone});
  
  document.getElementById('rain-container').appendChild(droplet);
}

  }
}

</script>

<style scoped>

#rain-container {
  position: absolute;
  top: -50%;
  left: -14%;
  width: 1543px;
  z-index: 1 !important;
  height: 1500px;
  transform: rotate(30deg);
}

article {
  height: 100vh;
}

.parent {
    display: grid;
    position: relative;

}

footer {
  height: 550px;
  position: fixed;
  bottom: 0;
}

.child {
  grid-area: 1 / 1 / 2 / 2;
  height: 0;
}

.layer5 {
  z-index: 2;
}

.layer3 {
  z-index: 3;
}

.layer4 {
  z-index: 11;
}

.layer1 {
  z-index: 1;
}

.layer2 {
  z-index: 10;
}

.layer11 {
  z-index: 12;
}

.layer12 {
  z-index: 13;
}

.layer8 {
  z-index: 14;
}

.layer9 {
  z-index: 15;
}

.bg {
  background-image: url("../assets/images/backgroundsmall.png");
  height: 100vh;
  background-position: center;
  background-repeat: repeat;
  background-size: cover;
}

img {
  width: 100%;
}

/* Mobile first queries */

/* Larger than mobile */
@media (min-width: 400px) {

}

/* Larger than phablet */
@media (min-width: 550px) {

}

/* Larger than tablet */
@media (min-width: 750px) {
  footer {
    height: 200px;
    position: fixed;
    bottom: 0;
  }
}

/* Larger than desktop */
@media (min-width: 1024px) {
  footer {
    height: 550px;
    position: fixed;
    bottom: 0;
  }
}

/* Larger than Desktop HD */
@media (min-width: 1200px) {

}
</style>
