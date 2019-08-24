<template>
  <!-- Footer -->
  <div class="footer agileits w3layouts" id="footer">
    <div class="container" id="cont">

      <div class="col-md-6 col-sm-6 agileits w3layouts footer-grids">
        <div class="col-md-4 col-sm-4 agileits w3layouts footer-grid footer-grid-1 wow fadeInUp">
          <ul class="agileits w3layouts">
            <li class="agileits w3layouts">5 Star Hotels</li>
            <li class="agileits w3layouts">Beach Resorts</li>
            <li class="agileits w3layouts">Beach Houses</li>
            <li class="agileits w3layouts">Water Houses</li>
          </ul>
        </div>
        <div class="col-md-4 col-sm-4 footer-grid agileits w3layouts footer-grid-2 wow fadeInUp">
          <ul class="agileits w3layouts">
            <li class="agileits w3layouts"><a href="gallery.html">Bahamas</a></li>
            <li class="agileits w3layouts"><a href="gallery.html">Hawaii</a></li>
            <li class="agileits w3layouts"><a href="gallery.html">Miami</a></li>
            <li class="agileits w3layouts"><a href="gallery.html">Ibiza</a></li>
          </ul>
        </div>
        <div class="col-md-4 col-sm-4 footer-grid footer-grid-2 agileits w3layouts wow fadeInUp">
          <ul class="agileits w3layouts">
            <li class="agileits w3layouts"><a href="index.html">Home</a></li>
            <li class="agileits w3layouts"><a href="about.html">About</a></li>
            <li class="agileits w3layouts"><a href="cuisines.html">Cuisines</a></li>
            <li class="agileits w3layouts"><a href="booking.html">Contact</a></li>
          </ul>
        </div>
        <div class="clearfix"></div>
      </div>

      <div class="col-md-6 col-sm-6 agileits w3layouts footer-grids newsletter wow fadeInUp">
        <h4>Stay Connected</h4>
        <p>Subscribe to our newsletter and get informed of our newest projects.</p>
        <form action="#" method="post">
          <input type="text" placeholder="Email" name="Email" required="">
        </form>
      </div>



      <div class="clearfix"></div>

    </div>
    <div class="clearfix"></div>
    <div style="height: 100px;margin-top: 5px"></div>
  </div>

  <!-- //Footer -->
</template>

<script>
  export default {
    name: "app-footer",
    data(){
      return{
        copyright:"Copyright 2019 Hotel Demo"
      }
    }
  }

</script>

<style scoped>
  #footer{
    height: 250px;
  }
  p{
    text-align: center;
  }
  .padding{
    padding-top: 2%;
  }
</style>
