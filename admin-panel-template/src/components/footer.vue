<template>
  <div>
    <footer class="footer">
      <div class="container-fluid">
        <div class="row">
          <div class="col-md-6 footer-copyright">
            <p class="mb-0">Copyright 2022 © Endless All rights reserved.</p>
          </div>
          <div class="col-md-6">
            <p class="pull-right mb-0">Hand crafted & made with<i class="fa fa-heart"></i></p>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
  import json from '../data/menu'
export default {
  name: 'footerpage',
  data(){
    return{
      customizer :false,
      data:"data:text/json;charset=utf-8," + encodeURIComponent(JSON.stringify(json)),
    }
  }
}
</script>
