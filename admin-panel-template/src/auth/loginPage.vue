<template>
 <div class="page-wrapper">
        <div class="container-fluid p-0">
               <div class="authentication-main">
                <div class="row">
                    <div class="col-md-12">
                        <div class="auth-innerright">
                            <div class="authentication-box">
                                <div class="text-center"><img alt="" src="../assets/images/endless-logo.png"></div>
                                <div class="card mt-4">
                                    <div class="card-body">
                                        <div class="text-center">
                                            <h4>LOGIN</h4>
                                            <h6>Enter your Username and Password </h6>
                                        </div>
                                           <form class="theme-form">
                                            <div class="form-group">
                                                <label class="col-form-label pt-0">Your Name</label>
                                                 <input v-model="email" class="form-control" type="email" placeholder="Test@gmail.com">
                                            </div>
                                            <div class="form-group">
                                                <label class="col-form-label">Password</label>
                                                <input v-model="password" :type="type" class="form-control" name="login[password]"
                      placeholder="*********">
                    <div class="show-hide"><span class="show" @click="showPassword"> </span></div>
                                            </div>
                                             <div class="checkbox p-0">
                                                <input id="checkbox1" type="checkbox">
                                                <label for="checkbox1">Remember me</label>
                                            </div>
                                             <div class="form-group form-row mt-3 mb-0">
                                                
                                                    <button class="btn btn-primary btn-block" type="button" @click="doLogin">Sign in </button>
                                            </div>
                                             <div class="form-group form-row mt-3 mb-0">
                                                <button class="btn btn-secondary btn-block" type="button">Login With
                                                    Auth0
                                                </button>
                                            </div>
                                            <div class="login-divider"></div>
                                             <div class="social mt-3">
                                                <div class="form-group btn-showcase d-flex">
                                                    <button 
                                                        class="btn social-btn btn-fb d-inline-block"><i
                                                            class="fa fa-facebook"></i></button>
                                                    <button 
                                                        class="btn social-btn btn-twitter d-inline-block"><i
                                                            class="fa fa-google"></i></button>
                                                    <button 
                                                        class="btn social-btn btn-google d-inline-block"><i
                                                            class="fa fa-twitter"></i></button>
                                                    <button 
                                                        class="btn social-btn btn-github d-inline-block"><i
                                                            class="fa fa-github"></i></button>
                                                </div>
                                            </div>
                                           </form>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
               </div>
        
        </div>
 </div>

 
</template>
<script>

export default {
  data() {
    return{
      type: 'password',
      email: "test@admin.com",
      password: "test@123456",
    }
   },
   
   methods: {
    showPassword: function() {
        if (this.type === 'password') {
          this.type = 'text';
        } else {
          this.type = 'password';
        }
      },
      doLogin() {
         if (this.email === "test@admin.com" || this.password === "test@123456") {
          
        localStorage.setItem('user',this.email)
           this.$router.push('/');
         } else {
           this.$toasted.show('Oops...' + err.message, {theme: 'bubble',   position: "bottom-right",   type: 'error', duration: 2000});
          
         }
      },
      
   }
}
</script>