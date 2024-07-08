<template>
    <!-- //hero section -->
    <section class="hero">
        <div class="hero-text">
            <h1>SmartWatch</h1>
            <h4>Element series</h4>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima deserunt deleniti ipsum eligendi pariatur quos eaque corrupti sint perspiciatis maiores.</p>
  
            <div class="hero-in">
                <div class="box">
                    <h3>White</h3>
                    <h5>Element</h5>
                    <img src="https://shorturl.at/kOHxj" alt="">
                </div>
                <div class="box">
                    <h3>White</h3>
                    <h5>Element</h5>
                    <img src="https://shorturl.at/kOHxj" alt="">
                </div>
                <div class="box">
                    <h3>White</h3>
                    <h5>Element</h5>
                    <img src="https://shorturl.at/kOHxj" alt="">
                </div>
            </div>
        </div>
  
        <div class="hero-img">
            <img src="https://shorturl.at/wsuBd" alt="">
        </div>
    </section>
  
    <div class="down-arrow">
        <i class='bx bx-down-arrow-alt'></i>
    </div>
  </template>
  
  <script>
  import { onMounted, ref, computed } from 'vue';
  import ScrollReveal from 'scrollreveal';
  
  export default {
    setup() {
        const isDarkmode = ref(false);
        const isMenu = ref(false);
  
        const toggleMenu = () => {
            isMenu.value = !isMenu.value;
        };
  
        const toggleDarkMode = () => {
            isDarkmode.value = !isDarkmode.value;
  
            if (isDarkmode.value) {
                document.body.classList.add('color');
            } else {
                document.body.classList.remove('color');
            }
        };
  
        const darkModeIcon = computed(() => (isDarkmode.value ? 'bx bx-sun' : 'bx bx-moon'));
  
        onMounted(() => {
            window.onscroll = () => {
                const menubar = document.querySelector('#menu-icon');
                const navlist = document.querySelector('.navlist');
                if (menubar && navlist) {
                    menubar.classList.remove('bx-x');
                    navlist.classList.remove('open');
                }
            };
  
            const sr = ScrollReveal({
                distance: '70px',
                duration: 2700,
                reset: true
            });
            sr.reveal('.hero-text', { delay: 200, origin: 'bottom' });
            sr.reveal('.hero-img', { delay: 350, origin: 'top' });
            sr.reveal('.down-arrow', { delay: 450, origin: 'right' });
        });
  
        return { toggleDarkMode, isMenu, toggleMenu, darkModeIcon };
    }
  }
  </script>
  
  <style>
  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    text-decoration: none;
  }
  :root {
    --text-color: #000000;
    --bg-color: #e5e5e5;
    --main-color: #f29494;
    --second-color: #fff;
    --other-color: #868686;
    --big-font: 5.5rem;
    --p-font: 1rem;
  }
  body {
    background: var(--bg-color);
    color: var(--text-color);
  }
  .h-main {
    display: flex;
    align-items: center;
  }
  .hero {
    position: relative;
    width: 100%;
    height: 100vh;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    align-items: center;
    gap: 1rem;
  }
  .hero-img {
    height: 800px;
    width: 800px;
  }
  .hero-img img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }
  .hero-in {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(100px, auto));
    align-items: center;
    text-align: center;
    gap: 30px;
  }
  .hero-text h1 {
    font-size: var(--big-font);
    line-height: 1.3;
    font-weight: 800;
  }
  .hero-text h4 {
    margin: 5px 0 20px;
    color: var(--main-color);
    text-transform: uppercase;
    letter-spacing: 10px;
    font-size: 22px;
    font-weight: 400;
  }
  .hero-text p {
    color: var(--other-color);
    font-size: var(--p-font);
    font-weight: 500;
    line-height: 26px;
    max-width: 550px;
    margin-bottom: 4rem;
  }
  .box {
    background: var(--second-color);
    padding: 25px 40px;
    border-radius: 1rem;
    box-shadow: rgba(33, 35, 38, 0.1) 0px 10px 10px -10px;
    transition: all ease .55s;
    cursor: pointer;
  }
  .box img {
    max-width: 100%;
    height: auto;
  }
  .box h3 {
    font-size: 30px;
    font-weight: 700;
    margin-bottom: 7px;
  }
  .box h5 {
    color: var(--main-color);
    font-size: 15px;
    font-weight: 400;
    letter-spacing: 4px;
  }
  .box:hover {
    transform: translateY(-5px) scale(1.1);
  }
  .down-arrow {
    position: absolute;
    bottom: 3.5rem;
    right: 9%;
  }
  .down-arrow i {
    padding: 14px;
    color: var(--bg-color);
    background: var(--text-color);
    font-size: 25px;
    border-radius: 3rem;
    cursor: pointer;
    transition: all ease .55s;
  }
  .down-arrow i:hover {
    background: var(--main-color);
    transform: translateY(5px);
  }
  body.color {
    --text-color: #fff;
    --bg-color: #08162a;
    --second-color: #2b3544;
  }
  
  @media (max-width: 1600px) {
    section {
        padding: 0 5%;
    }
  }
  @media (max-width: 1470px) {
    .hero-img {
        height: 700px;
        width: 700px;
    }
  }
  @media (max-width: 1600px) {
    :root {
        --big-font: 4rem;
        --p-font: 15px;
    }
    .box h3 {
        font-size: 20px;
        margin-bottom: 2px;
    }
    .hero-img {
        width: 600px;
        height: 600px;
    }
  }
  @media (max-width: 1230px) {
    .hero {
        grid-template-columns: 1fr;
        height: auto;
    }
    .hero-text {
        order: 2;
    }
    section {
        padding: 50px 5%;
    }
    .hero-img {
        margin: auto;
        height: auto;
        width: auto;
    }
    .hero-img img {
        width: 100%;
        height: auto;
        max-width: 650px;
    }
    .down-arrow {
        display: none;
    }
  }
  @media (max-width: 600px) {
    .hero-in {
        grid-template-columns: repeat(auto-fit, minmax(190px, auto));
        gap: 18px;
    }
    .box {
        padding: 10px 30px;
    }
    :root {
        --big-font: 3rem;
        --p-font: 14px;
    }
    #menu-icon {
        margin-right: 5px;
    }
  }
  </style>
  