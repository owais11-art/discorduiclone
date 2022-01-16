<template>
  <div class="home">
    <div class="left-bg"></div>
    <div class="right-bg"></div>
    <img src="../assets/images/left_bg_landing.svg" alt="" class="mb-img">
    <div class="content-layer">
      <Navbar @onToggle='toggler' />
      <div class="hero-content">
        <h1>IMAGINE A PLACE...</h1>
        <p>...where you can belong to a school club, a gaming group, or a worldwide art community.</p>
        <p>Where just you and a handful of friends can spend time together. A place that makes it easy</p>
        <p>to talk every day and hang out more often.</p>
        <div  class="c-btns">
          <div v-for="(btnn, index) in buttons" :key="index">
            <Button :text="btnn.text" :bgColor="btnn.bgColor" :color="btnn.color" 
            :size="btnn.size" :download="btnn.download" margin="40px" />
          </div>
        </div>
      </div>
    </div>
  </div>
  <div v-for="(cnt, index) in cardContent" :key="index">
    <Cards :content="cnt" :ind="index" />
  </div>
  <div class="screen">
    <div class="sreen-content">
      <h1>RELIABLE TECH FOR STAYING CLOSE</h1>
      <p>Low-latency voice and video feels like you're in the same room. Wave hello over video, watch friends stream their <br/> games, or gather up and have a drawing session with screen share.</p>
    </div>
    <img src="../assets/images/screen.svg" alt="">
    <div class="lower-content">
      <h2>Ready to start your journey?</h2>
      <Button text="Download for Windows" bgColor="#5865f2" color="#fff" 
        size="1.3rem" download=true margin="20px" />
    </div>
  </div>
  <aside v-if="showSidebar">
    <div class="aside-nav">
      <i class="bi bi-x" @click="toggler"></i>
    </div>
    <ul class="nav-items">
      <li><a href="#">Download</a></li>
      <li><a href="#">Nitro</a></li>
      <li><a href="#">Safety</a></li>
      <li><a href="#">Support</a></li>
      <li><a href="#">Blog</a></li>
      <li><a href="#">Careers</a></li>
    </ul>
  </aside>
  <Footer />
</template>

<script>
import Navbar from '../components/Navbar.vue';
import Cards from '../components/Cards.vue';
import Footer from '../components/Footer.vue';
import Button from '../components/Button.vue';
import { ref } from '@vue/reactivity';
export default {
  name: 'Home',
  components: {
    Navbar,
    Button,
    Cards,
    Footer
  },
  setup(){
    let showSidebar = ref(false)
    let buttons = [
      {
        text: 'Download for Windows',
        color: '#23272a',
        bgColor: '#fff',
        size: '1.3rem',
        download: true
      },
      {
        text: 'Open Discord in Your Browser',
        color: '#fff',
        bgColor: '#2f3136',
        size: '1.3rem',
        download: false
      }
    ];
    const toggler = () => {
      showSidebar.value = !showSidebar.value;
    }
    let cardContent = ref([
      {
        contentHead: 'Create an invite-only place where you belong',
        contentPara: `Discord servers are organized into topic-based 
                      channels where you can collaborate, share, and 
                      just talk about your day without clogging up a group chat.`,
        contentImg: "dim1"
      },
      {
        contentHead: 'Where hanging out is easy',
        contentPara: `Grab a seat in a voice channel when you're free. 
                      Friends in your server can see you're around and 
                      instantly pop in to talk without having to call.`,
        contentImg: 'dim2'
      },
      {
        contentHead: 'From few to a fandom',
        contentPara: `Get any community running with moderation tools 
                      and custom member access. Give members special 
                      powers, set up private channels, and more.`,
        contentImg: 'dim3'
      }
    ]);
    return {buttons, cardContent, showSidebar, toggler};
  }
}
</script>
<style>
  .mb-img{
    display: none;
  }
  .home{
    position: relative;
    width: 100%;
    height: 100vh;
    background: #404eed url('../assets/images/landing_bg.svg')no-repeat center center / cover;
  }
  aside{
    position: absolute;
    padding: 20px;
    top: 0;
    right: 0;
    height: 100%;
    width: 373px;
    background: #f6f6f6;
    z-index: 100;
  }
  aside .aside-nav .bi-x{
    font-size: 2rem;
    cursor: pointer;
  }
  aside ul{
    display: flex;
    flex-direction: column;
    gap: 20px;
  }
  aside ul li{
    list-style-type: none;
  }
  aside ul li a{
    color: black;
    text-decoration: none;
  }
  .home .left-bg{
    position: absolute;
    width: 300px;
    height: 300px;
    background: url('../assets/images/left_bg_landing.svg')no-repeat center right / cover;
    bottom: 0;
    left: 0px;
  }
  .home .right-bg{
    position: absolute;
    width: 300px;
    height: 300px;
    background: url('../assets/images/right_bg_landing.svg')no-repeat center left / cover;
    bottom: 0;
    right: 0px;
  }
  .home .content-layer{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
  .home .content-layer .hero-content{
    color: #fff;
    text-align: center;
  }
  .home .content-layer .hero-content h1{
    font-weight: 1000;
    font-size: 4.5rem;
    margin-top: 10%;
    margin-bottom: 15px;
  }
  .home .content-layer .hero-content p{
    font-size: 1.3rem;
    margin-top: 13px;
  }
  .c-btns{
    display: flex;
    gap: 20px;
    justify-content: center;
    margin-top: 20px;
  }
  .screen{
    text-align: center;
    padding: 40px;
    background: #f6f6f6;
  } 
  .screen h1{
    font-weight: bolder;
    font-size: 4rem;
    margin-top: 60px;
  }
  .screen p{
    font-size: 1.5rem;
    color: #23272a;
    line-height: 1.5;
  }
  .screen img{
    width: 100%;
    margin: 40px 0;
  } 
  .screen .lower-content h2{
    font-size: 1.8rem;
    margin: 20px 0;
  }
  @media(min-width: 751px) and (max-width: 900px){
    .screen h1{
    font-weight: bolder;
    font-size: 2rem;
    }
    .screen p{
      font-size: 1rem;
      color: #23272a;
      line-height: 1.5;
    }
    .mb-img{
      display: none;
    }
    .home .right-bg{
      display: block;
    }
    .home .content-layer .hero-content h1{
      font-weight: 600;
      font-size: 3rem;
    }
    .home .content-layer .hero-content p{
      font-size: 1rem;
    }
    .home .content-layer .hero-content{
      text-align: left;
      padding-left: 10px;
    }
  }
  @media(max-width: 750px){
    .screen{
      text-align: left;
    }
    .screen h1{
    font-weight: bolder;
    font-size: 1.6rem;
    }
    .screen p{
      font-size: 0.8rem;
      color: #23272a;
      line-height: 1.5;
    }
    .home .content-layer .hero-content{
      text-align: left;
      padding-left: 10px;
    }
    .home .content-layer .hero-content h1{
      font-weight: 600;
      font-size: 2rem;
    }
    .home .content-layer .hero-content p{
      font-size: 1rem;
    }
    .c-btns{
      flex-direction: column;
    }
    .home .right-bg, .home .left-bg{
      display: none;
    }
    .mb-img{
      display: block;
      position: absolute;
      bottom: 0;
      left: -50px;
      width: 75%;
      min-width: 390px;
    }
    
  }
</style>
