<template>
     <div class="loader-wrapper"  :class="{'loderhide' : !show }">
      <div class="loader bg-white">
        <div class="whirly-loader"> </div>
      </div>
    </div>
</template>

<script>
export default {
      data(){
    return{
      show: true
    }
  },
   mounted() {
      this.timeOut();
      Userauth.handleAuthentication().then(() =>{
        window.location.href = '/endless/dashboard/default'}
      )
    },
    methods: {
         timeOut(){
            var self = this;
            setTimeout(function(){
                self.show = false;
            }, 1000);
      }
    }
};
</script>

<style lang="scss" scoped>
.loader-wrapper.loderhide {
  display: none;
}
</style>
