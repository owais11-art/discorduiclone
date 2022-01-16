<template>
  <div class="main-container">
      <div class="register-container">
          <form>
              <div class="logo">
                <img src="../components/img/discord_icon_3.svg" alt="discord-logo">
                <span>
                    <h3>Discord</h3>
                </span>
            </div>
            <div class="greetings">
                <h2>Create an account</h2>
            </div>
            <div class="form">
                <label>EMAIL</label>
                <div class="form-control">
                    <input type="email">
                </div>
                <label>USERNAME</label>
                <div class="form-control">
                    <input type="text">
                </div>
                <label>PASSWORD</label>
                <div class="form-control">
                    <input type="password">
                </div>
                <div class="form-control submit">
                    <input type="submit" value="Continue">
                </div>
                <small>
                    <router-link :to="{name: 'Login'}">
                        Already have an account?
                    </router-link>
                </small>
            </div>
          </form>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
    .main-container .register-container .qr-code{
        display: none;
    }
    .main-container{
        width: 100%;
        height: 100vh;
    }
    .main-container .register-container{
        width: 100%;
        height: 100%;
        background: #36393f;
        padding: 50px 20px;
    }
    .main-container .register-container .logo{
        display: flex;
        justify-content: center;
        align-items: center;
        color: #fff;
    }
    .main-container .register-container .greetings{
        color: #fff;
        margin-top: 60px;
    }
    .main-container .register-container .greetings h2{
        margin-bottom: 10px; 
        text-align: center;
    }
    .main-container .register-container a{
        color: #00aff4;
        text-decoration: none;
    }
    .main-container .register-container .form{
        margin-top: 30px;
    }
    .main-container .register-container .form label{
        color: #8e9297;
        font-size: 0.8rem;
        font-weight: bold;
        letter-spacing: 1px;
    }
    .main-container .register-container .form .form-control{
        margin: 10px 0;
        border: 2px solid #202225;
        width: 100%;
    }
    .main-container .register-container .form .form-control input{
        width: 100%;
        padding: 8px;
        border: none;
        outline: none;
        background: #292b2f;
        color: #8e9297;
    }
    .main-container .register-container .form .form-control input[type="submit"]{
        background: #5865f2;
        color: #fff;
        font-weight: bold;
        padding: 15px;
        cursor: pointer;
    }
    .main-container .register-container .form .submit{
        border: none;
        margin-top: 25px;
    }
    @media(min-width: 750px){
        .main-container .register-container .logo{
            display: none;
        }
        .main-container{
            display: grid;
            place-items: center;
            background: url('../components/img/login_bg.svg')no-repeat center center / cover;
        }
        .main-container .register-container .form{
            width: 100%;
        }
        .main-container .register-container{
            width: 480px;
            height: auto;
            padding: 30px 20px;
        }
        .main-container .register-container .greetings{
            margin-top: 0;
        }
    }
</style>