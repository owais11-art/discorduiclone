<template>
  <nav>
      <div class="nav-container">
          <div class="logo">
              <img src="../img/discord_icon.svg" alt="discord-logo">
              <span>
                  <h2>Discord</h2>
              </span>
          </div>
          <ul class="nav-items">
              <li><a href="#">Download</a></li>
              <li><a href="#">Nitro</a></li>
              <li><a href="#">Safety</a></li>
              <li><a href="#">Support</a></li>
              <li><a href="#">Blog</a></li>
              <li><a href="#">Careers</a></li>
          </ul>
          <div class="bt-list">
            <Button text='Open Discord' bgColor='#fff' color='#23272a' />
            <i class="bi bi-list" @click="onClick"></i>
          </div>
      </div>
  </nav>
</template>

<script>
import Button from '../Button.vue';
export default {
    name: 'Navbar',
    components:{
        Button
    },
    emits: ['onToggle'],
    setup(props, { emit }){
        const onClick = () => {
            emit('onToggle');
        };
        return {onClick};
    }

}
</script>


<style>
    .bt-list{
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 10px;
        cursor: pointer;
    }
    .bi-list {
        color: #fff;
        font-size: 2rem;
        display: none;
    }
    nav{
        width: 100%;
        padding-top: 10px;
    }
    nav .nav-container{
        width: 90%;
        margin: 0 auto;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    nav .nav-container .logo{
        display: flex;
        align-items: center;
        color: #fff;
        cursor: pointer;
    }
    nav .nav-container .nav-items{
        display: flex;
        gap: 40px;
    }
    nav .nav-container .nav-items li{
        list-style-type: none;
    }
    nav .nav-container .nav-items li a{
        color: #fff;
        font-weight: bold;
        text-decoration: none;
    }
    nav .nav-container .nav-items li a:hover{
        text-decoration: underline;
    }
    @media(max-width: 900px){
        .bi-list{
            display: inline;
        }
        nav .nav-container .nav-items{
            display: none;
        }
    }
</style>