<template>
  <div class="container-bg">
    <div class="in-progress">
      <img class="img-ip" src="../assets/images/nge.gif">
      <h1 style="font-size:10vw;">Oof</h1>
      <p style="font-size:5vw;">Tiph is still working on the responsive and adding a couple of improvements</p>
      <p style="font-size:5vw;">Check it on desktop or wait for the update :)</p>
    </div>
    <article>
      <footer>
        <div class="container_row parent">
          <div class="layer1 child">
            <img ref="l1image" class="l1image" src="../assets/images/eva000.png" alt="" >  
          </div>

          <div class="layer2 child">
            <img ref="l2image" class="l2image" src="../assets/images/eva21.png" alt="" >  
          </div>

          <div class="layer3 child">
            <img ref="l3image" class="l3image" src="../assets/images/eva1.png" alt="" >  
          </div>
          </div>
      </footer>
    </article>
  </div>
</template>

<script>
  import { TimelineMax } from "gsap"
  export default { 

    data() {
      return {
        timeline: null
      };
    },

  mounted() {
    var l2image = '.l2image';
    new TimelineMax({ repeat: -1 })
    .to(l2image, 15, {y:-200}, 0)
    }
  }
</script>

<style scoped>

.in-progress {
  display: none;
}

.img-ip {
  display: none;
}

article {
  height: 100vh;
}

.parent {
    display: grid;
    position: relative;

}

.child {
  grid-area: 1 / 1 / 2 / 2;
  height: 0;
}

.layer1 {
  z-index: 1;
}

.layer2 {
  z-index: 2;
}

.layer3 {
  z-index: 3;
}


img {
  width: 100%;
}

@media (max-width: 1024px) {
  h1 {
    color: white;
    text-align: center;
  }

  p {
    color: white;
    text-align: center;
  }

  article {
      display: none;
    }

  .in-progress {
    display: block;
    background-color: black;
  }

  .img-ip {
    display: block;
  }
}

</style>
