<script setup>
import { ref } from 'vue'

const isVisible = ref(false)

const changeIcon = () => {
  if (isVisible.value == true) {
    return { backgroundImage: 'url(/assets/images/icon-menu-close.svg)' }
  }
}

const animateNavContainer = () => {
  if (isVisible.value == true) {
    return {
      transform: 'translateX(0%)',
    }
  }
}

const toggleVisibility = () => {
  isVisible.value = !isVisible.value
}
</script>

<template>
  <main>
    <div class="container">
      <div class="overlay" v-show=isVisible></div>
      <div class="header">
        <img src="./assets/images/logo.svg" alt="">
        <div aria-controls="navigation" class="menu" :style="changeIcon()" @click="toggleVisibility"></div>
        <div class="navigation-container" :style="animateNavContainer()">
          <ul aria-expanded="false" id="navigation" class="nav-list">
            <li><a href="#"></a>Home</li>
            <li><a href="#"></a>New</li>
            <li><a href="#"></a>Popular</li>
            <li><a href="#"></a>Trending</li>
            <li><a href="#"></a>Categories</li>
          </ul>
        </div>
      </div>

      <div class="grid-container">
        <div class="item item-1">
          <div></div>
          <div>
            <h1>The Bright Future of Web 3.0?</h1>
          </div>
          <div>
            <p>We dive into the next evolution of the web that claims to put the power of the platforms back into the
              hands of the people.
              But is it really fulfilling its promise?</p>
            <button>READ MORE</button>
          </div>
        </div>
        <div class="item item-2">
          <h1>New</h1>
          <div class="new-categories">
            <div class="new-category">
              <h4>Hydrogen VS Electric Cars</h4>
              <p>Will hydrogen-fueled cars ever catch up to EVs?</p>
            </div>
            <hr>
            <div class="new-category">
              <h4>The Downsides of AI Artistry</h4>
              <p>What are the possible adverse effects of on-demand AI image generation?</p>
            </div>
            <hr>
            <div class="new-category">
              <h4>Is VC Funding Drying Up?</h4>
              <p>Private funding by VC firms is down 50% YOY. We take a look at what that means.</p>
            </div>
          </div>
        </div>
        <div class="item item-3 bottom-card">
          <img src="./assets/images/image-retro-pcs.jpg" alt="" class="bottom-card-image">
          <div class="bottom-card-info">
            <h3>01</h3>
            <h4>Reviving Retro PCs</h4>
            <p>What happens when old PCs are given modern upgrades?</p>
          </div>
        </div>
        <div class="item item-4 bottom-card">
          <img src="./assets/images/image-top-laptops.jpg" alt="" class="bottom-card-image">
          <div class="bottom-card-info">
            <h3>02</h3>
            <h4>Top 10 Laptops of 2022</h4>
            <p>Our best picks for various needs and budgets.</p>
          </div>
        </div>
        <div class="item item-5 bottom-card">
          <img src="./assets/images/image-gaming-growth.jpg" alt="" class="bottom-card-image">
          <div class="bottom-card-info">
            <h3>03</h3>
            <h4>The Growth of Gaming</h4>
            <p>How the pandemic has sparked fresh opportunities.</p>
          </div>
        </div>
      </div>
      <div class="attribution">
        Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>.
        Coded by <a href="https://www.twitter.com/tedbankong">Ted Bankong</a>.
      </div>
    </div>
  </main>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700;800&display=swap');

* {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
}

main {
  height: 100%;
  min-height: 100%;
  width: 100%;
  padding: 0px 10%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.container {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 30px;
}

.header {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-top: 30px;
  padding-bottom: 30px;
  position: sticky;
  top: 0;
  background-color: hsl(100, 100%, 100%);
}

.menu {
  display: none;
}

.nav-list {
  display: flex;
  list-style: none;
}

.nav-list li {
  margin-inline: 10px;
  transition: all 0.2s ease-out;
}

.nav-list li:hover {
  color: hsl(5, 85%, 63%);
  cursor: pointer;
}

.nav-list li:last-child {
  margin-right: 0;
}

.overlay {
  background-color: hsl(0, 0%, 0%, 0.77);
  z-index: 100;
  position: absolute;
}

.grid-container {
  width: 100%;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 450px 100px;
  gap: 20px;
  margin-inline: auto;
}

.item-1 {
  grid-column: span 2;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: 1fr 1fr;
  gap: 30px 0px;
}

.item-1 div:first-child {
  grid-column: span 2;
  background-image: url(./assets/images/image-web-3-desktop.jpg);
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

.item-1 div:nth-child(2) {
  background-color: white;
  padding-right: 30px;
  display: flex;
  align-items: center;
  justify-content: start;
}

.item-1 div:nth-child(2) h1 {
  font-weight: 800;
  font-size: 45px;
  line-height: 1;
  color: hsl(240, 100%, 5%);
}

.item-1 div:last-child {
  background-color: white;
  display: flex;
  flex-direction: column;
  align-items: start;
  justify-content: space-evenly;
}

.item-1 div:last-child p {
  font-family: 'Inter', sans-serif;
  font-weight: 400;
  color: hsl(240, 100%, 5%);
  font-size: 13px;
}

.item-1 div:last-child button {
  height: 50px;
  width: 150px;
  border: none;
  color: white;
  background-color: hsl(5, 85%, 63%);
  letter-spacing: 2px;
  transition: all 0.2s ease-out;

}

.item-1 div:last-child button:hover {
  background-color: hsl(240, 100%, 5%);
  cursor: pointer;
}

.item-2 {
  background-color: hsl(240, 100%, 5%);
  display: flex;
  flex-direction: column;
  align-items: start;
  justify-content: space-evenly;
  padding: 20px;
  padding-right: 50px;
}

.item-2 h1 {
  font-weight: 700;
  font-size: 30px;
  color: hsl(35, 77%, 62%);
}

.new-categories hr {
  margin-top: 30px;
  margin-bottom: 30px;

}

.new-category h4 {
  font-weight: 700;
  color: hsl(36, 100%, 99%);
  margin-bottom: 10px;
  line-height: 1;
}

.new-category h4:hover {
  cursor: pointer;
  color: hsl(35, 77%, 62%);
}

.new-category p {
  font-weight: 400;
  font-size: 12px;
  color: hsl(36, 100%, 99%, 0.77);

}

.bottom-card {
  display: flex;
  align-items: center;
}

.bottom-card-image {
  width: 20%;
  height: 100%;
  background-repeat: no-repeat;
  object-fit: cover;
  object-position: center;
  margin-right: 30px;
}

.bottom-card-info {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.bottom-card-info h3 {
  font-weight: 700;
  color: hsl(233, 8%, 79%);
  font-size: 20px;

}

.bottom-card-info h4 {
  font-size: 13px;
  font-weight: 700;
  color: hsl(240, 100%, 5%);
}

.bottom-card-info h4:hover {
  color: hsl(5, 85%, 63%);
  cursor: pointer;
}

.bottom-card-info p {
  font-size: 12px;
  font-weight: 400;
  color: hsl(240, 100%, 5%);
}

.attribution {
  padding-inline: 20px;
  text-align: center;
  margin-top: 50px;
}

.attribution a {
  text-decoration: none;
  color: hsl(5, 85%, 63%);
}

.attribution a:hover {
  color: hsl(35, 77%, 62%);
}

@media only screen and (max-width: 992px) {

  main {
    padding: 0px 15px 0px 15px;
  }

  .container {
    margin-bottom: 0px;
  }

  .menu {
    width: 60px;
    aspect-ratio: 1;
    display: block;
    background-image: url(./assets/images/icon-menu.svg);
    background-repeat: no-repeat;
    background-position: center;
    z-index: 9999;
    transition: all 0.3s ease-in;
  }

  .navigation-container {
    position: fixed;
    top: 0;
    bottom: 0;
    right: 0;
    width: 70%;
    height: 100%;
    z-index: 1000;
    background-color: hsl(36, 100%, 99%);
    transform: translateX(100%);
    transition: transform 350ms ease-out;
  }

  .nav-list {
    flex-direction: column;
    padding: 30vh 0px 0px 20px;
  }

  .nav-list li {
    font-size: 20px;
    margin-bottom: 10px;
  }

  .grid-container {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 0px;
  }

  .item-1 {
    display: flex;
    flex-direction: column;
    width: 100%;
    gap: 0px;
  }

  .item-1 div:first-child {
    background-image: url(./assets/images/image-web-3-mobile.jpg);
    aspect-ratio: 686 / 600;
    margin-bottom: 25px;
  }

  .item-1 div:nth-child(2) {
    margin-bottom: 25px;
  }

  .item-1 div:nth-child(2) h1 {
    font-size: 40px;
  }

  .item-1 div:last-child {
    justify-content: start;
    margin-bottom: 60px;
  }

  .item-1 div:last-child p {
    margin-bottom: 15px;
  }

  .item-2 {
    margin-bottom: 60px;
  }

  .item-2 h1 {
    margin-bottom: 30px;
  }

  .bottom-card {
    margin-bottom: 20px;
  }

  .bottom-card-image {
    width: 30%;
    margin-right: 20px;
  }

  .bottom-card-info h3 {
    font-size: 25px;
  }

  .bottom-card-info h4 {
    font-size: 15px;
  }

  .item-5 {
    margin-bottom: 70px;
  }

  .attribution {
    margin-top: 0px;
  }
}

@media only screen and (min-width: 600px) and (max-width: 992px) {

  main {
    padding: 0px 10%;
  }

  .nav-list li {
    font-size: 30px;
  }

  .item-1 div:nth-child(2) h1 {
    font-size: 45px;
  }

  .item-1 div:last-child p {
    font-size: 20px;
  }

  .bottom-card-image {
    width: 20%;
    margin-right: 20px;
  }

  .bottom-card-info h3 {
    font-size: 30px;
  }

  .bottom-card-info h4 {
    font-size: 20px;
  }

  .bottom-card-info p {
    font-size: 15px;
  }
}
</style>
