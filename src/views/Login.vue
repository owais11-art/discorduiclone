<template>
  <div class="main-container">
      <div class="login-container">
          <form>
              <div class="logo">
                <img src="../components/img/discord_icon_3.svg" alt="discord-logo">
                <span>
                    <h3>Discord</h3>
                </span>
            </div>
            <div class="greetings">
                <h2>Welcome back!</h2>
                <p>We're so excited to see you again!</p>
            </div>
            <div class="form">
                <label>EMAIL</label>
                <div class="form-control">
                    <input type="email">
                </div>
                <label>PASSWORD</label>
                <div class="form-control">
                    <input type="password">
                </div>
                <small>Forgot your password?</small>
                <div class="form-control submit">
                    <input type="submit" value="Login">
                </div>
                <small><span class="account">Need an account?</span> 
                <router-link :to="{name: 'Register'}">
                    Register
                </router-link>
                </small>
            </div>
          </form>
          <div class="qr-code">
            <div class="img">
                <img src="../components/img/QR_code.png" alt="">
            </div>
            <h3>Log in with QR code</h3>   
            <p>Scan this with <span class="brand">Discord mobile app</span> to log in instantly</p>
          </div>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
    .main-container .login-container .qr-code{
        display: none;
    }
    .main-container{
        width: 100%;
        height: 100vh;
    }
    .main-container .login-container{
        width: 100%;
        height: 100%;
        background: #36393f;
        padding: 50px 20px;
    }
    .main-container .login-container .logo{
        display: flex;
        justify-content: center;
        align-items: center;
        color: #fff;
    }
    .main-container .login-container .greetings{
        color: #fff;
        margin-top: 60px;
    }
    .main-container .login-container .greetings h2{
        margin-bottom: 10px; 
    }
    .main-container .login-container small{
        color: #00aff4;
    }
    .main-container .login-container a{
        color: #00aff4;
        text-decoration: none;
    }
    .main-container .login-container .greetings p,
    .main-container .login-container .account{
        color: #8e9297;
    }
    .main-container .login-container .form{
        margin-top: 30px;
    }
    .main-container .login-container .form label{
        color: #8e9297;
        font-size: 0.8rem;
        font-weight: bold;
        letter-spacing: 1px;
    }
    .main-container .login-container .form .form-control{
        margin: 10px 0;
        border: 2px solid #202225;
    }
    .main-container .login-container .form .form-control input{
        width: 100%;
        padding: 8px;
        border: none;
        outline: none;
        background: #292b2f;
        color: #8e9297;
    }
    .main-container .login-container .form .form-control input[type="submit"]{
        background: #5865f2;
        color: #fff;
        font-weight: bold;
        cursor: pointer;
    }
    .main-container .login-container .form .submit{
        border: none;
        margin-top: 25px;
    }
    @media(min-width: 750px){
        .main-container .login-container .logo{
            display: none;
        }
        .main-container .login-container{
            display: flex;
            justify-content: center;
            gap: 10px;
        }
        .main-container .login-container .qr-code{
            display: block;
            color: #fff;
        }
        .main-container .login-container .qr-code .img{
            display: block;
            width: 150px;
            height: 150px;
            background: #fff;
            margin: auto;
            margin-top: 30px;
            margin-bottom: 20px;
        }
        .main-container .login-container .qr-code .img img{
            width: 100%;
        }
        .main-container .login-container .qr-code h3{
            text-align: center;
        }
        .main-container .login-container .qr-code p{
            margin-top: 20px;
            text-align: center;
            font-size: 0.8rem;
        }
        .main-container .login-container .qr-code .brand{
            font-weight: bold;
        }
        .main-container{
            display: grid;
            place-items: center;
            background: url('../components/img/login_bg.svg')no-repeat center center / cover;
        }
        .main-container .login-container{
            width: 600px;
            height: auto;
            padding: 30px 20px;
        }
        .main-container .login-container .greetings{
            margin-top: 0;
        }
    }
</style>