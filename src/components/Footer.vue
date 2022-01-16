<template>
  <footer>
      <div class="col-1">
          <h2 class="head">IMAGINE A <br/>PLACE</h2>
          <div class="social">
              <i class="bi bi-twitter"></i>
              <i class="bi bi-instagram"></i>
              <i class="bi bi-facebook"></i>
              <i class="bi bi-youtube"></i>
          </div>
      </div>
      <div class="col-2">
          <ul>
              <li class="head">Product</li>
              <li>Download</li>
              <li>Nitro</li>
              <li>Status</li>
          </ul>
      </div>
      <div class="col-3">
          <ul>
              <li class="head">Company</li>
              <li>About</li>
              <li>Jobs</li>
              <li>Branding</li>
              <li>Newsroom</li>
          </ul>
      </div>
      <div class="col-4">
          <ul>
              <li class="head">Resources</li>
              <li>College</li>
              <li>Support</li>
              <li>Safety</li>
              <li>Blog</li>
              <li>Feedback</li>
              <li>Developers</li>
              <li>StreamKit</li>
          </ul>
      </div>
      <div class="col-5">
          <ul>
              <li class="head">Policies</li>
              <li>Terms</li>
              <li>Privacy</li>
              <li>Cookie Settings</li>
              <li>Guidelines</li>
              <li>Acknowledgements</li>
              <li>Licenses</li>
              <li>Moderation</li>
          </ul>
      </div>
      <div class="break"></div>
      <div class="footer-nav">
          <div class="logo">
              <img src="./img/discord_icon_cpy.svg" alt="discord-logo">
              <span>
                  <h4>Discord</h4>
              </span>
          </div>
          <Button text='Open Discord' bgColor='#0000ee' color='#fff' />
      </div>
  </footer>
</template>

<script>
import Button from './Button.vue';
export default {
    name: 'Footer',
    components: {
        Button
    }
}
</script>

<style>
    footer{
        padding: 50px 30px;
        color: #fff;
        background: #202225;
        display: grid;
        grid-template-columns: repeat(5, 1fr);
    }
    footer .break{
        width: 100%;
        height: 1px;
        background: #0000ee;
        grid-column: 1 / -1;
        margin-top: 10px;
    }
    footer .footer-nav{
        grid-column: 1 / -1;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    footer .footer-nav .logo{
        display: flex;
        align-items: center;
    }
    footer ul{
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
    footer ul li {
        list-style-type: none;
    }
    footer ul li:not(.head){
        cursor: pointer;
    }
    footer ul li:not(.head):hover{
        text-decoration: underline;
    }
    footer h2{
        font-size: 2rem;
    }
    footer .head{
        color: #0000ee;
    }
    footer .social{
        display: inline-block;
        margin-top: 40px;
    }
    footer .social .bi{
        margin-right: 25px;
        font-size: 1.5rem;
        cursor: pointer;
    }
    @media(max-width: 1000px){
        footer{
            grid-template-columns: repeat(3, 1fr);
        }
        footer .col-1{
            grid-row: span 2;
        }
        footer div:not(.col-1){
            font-size: 0.8rem;
        }
    }
    @media(max-width: 700px){
        footer{
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }
        footer .col-1{
            grid-column: span 2;
        }
    }
</style>