<template>
  <div id="housecard">
    <div class="details agileits w3layouts">
      <div class="container">
        <div class="details-grids agileits w3layouts">
          <div class="col-md-4 col-sm-4 details-grid agileits w3layouts details-grid-1 wow slideInUp">
            <div class=" details-grid1 agileits w3layouts">
              <div class="details-grid-image agileits w3layouts">
                <img src="/static/images/project-1.jpg" alt="Agileits W3layouts">
              </div>
              <div class="details-grid-info agileits w3layouts">
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod	tempor incididunt ut labore et dolore magna aliqua ut enim ad minim veniam.</p>
              </div>
              <button class="btn btn-primary wow agileits w3layouts fadeInLeft" data-toggle="modal" data-target="#myModal">EXPLORE<span class="glyphicon agileits w3layouts glyphicon-arrow-right" aria-hidden="true"></span></button>
              <div class="clearfix"></div>
            </div>
          </div>
          <div class="col-md-4 col-sm-4 details-grid details-grid-2 wow agileits w3layouts slideInUp">
            <div class="details-grid2 agileits w3layouts">
              <div class="details-grid-image agileits w3layouts">
                <img src="/static/images/project-6.jpg" alt="Agileits W3layouts">
              </div>
              <div class="details-grid-info agileits w3layouts">
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod	tempor incididunt ut labore et dolore magna aliqua ut enim ad minim veniam.</p>
              </div>
              <button class="btn btn-primary wow agileits w3layouts fadeInLeft" data-toggle="modal" data-target="#myModal2">EXPLORE<span class="glyphicon agileits w3layouts glyphicon-arrow-right" aria-hidden="true"></span></button>
              <div class="clearfix"></div>
            </div>
          </div>
          <div class="col-md-4 col-sm-4 details-grid agileits w3layouts details-grid-3 wow slideInUp">
            <div class="details-grid3 agileits w3layouts">
              <div class="details-grid-image agileits w3layouts">
                <img src="/static/images/project-7.jpg" alt="Agileits W3layouts">
              </div>
              <div class="details-grid-info agileits w3layouts">
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod	tempor incididunt ut labore et dolore magna aliqua ut enim ad minim veniam.</p>
              </div>
              <button class="btn btn-primary agileits w3layouts wow fadeInLeft" data-toggle="modal" data-target="#myModal3">EXPLORE<span class="glyphicon agileits w3layouts glyphicon-arrow-right" aria-hidden="true"></span></button>
              <div class="clearfix"></div>
            </div>
          </div>
          <div class="clearfix"></div>
        </div>
        <div class="col-md-4 col-sm-4 details-grid agileits w3layouts details-grid-1 wow slideInUp">
          <div class=" details-grid1 agileits w3layouts">
            <div class="details-grid-image agileits w3layouts">
              <img src="/static/images/project-1.jpg" alt="Agileits W3layouts">
            </div>
            <div class="details-grid-info agileits w3layouts">
              <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod	tempor incididunt ut labore et dolore magna aliqua ut enim ad minim veniam.</p>
            </div>
            <router-link to="/gallery">
              <button class="btn btn-primary wow agileits w3layouts fadeInLeft" data-toggle="modal" data-target="#myModal">EXPLORE<span class="glyphicon agileits w3layouts glyphicon-arrow-right" aria-hidden="true"></span></button>
            </router-link>
            <div class="clearfix"></div>
          </div>
        </div>
        <div class="col-md-4 col-sm-4 details-grid details-grid-2 wow agileits w3layouts slideInUp">
          <div class="details-grid2 agileits w3layouts">
            <div class="details-grid-image agileits w3layouts">
              <img src="/static/images/project-6.jpg" alt="Agileits W3layouts">
            </div>
            <div class="details-grid-info agileits w3layouts">
              <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod	tempor incididunt ut labore et dolore magna aliqua ut enim ad minim veniam.</p>
            </div>
            <button class="btn btn-primary wow agileits w3layouts fadeInLeft" data-toggle="modal" data-target="#myModal2">EXPLORE<span class="glyphicon agileits w3layouts glyphicon-arrow-right" aria-hidden="true"></span></button>
            <div class="clearfix"></div>
          </div>
        </div>
        <div class="col-md-4 col-sm-4 details-grid agileits w3layouts details-grid-3 wow slideInUp">
          <div class="details-grid3 agileits w3layouts">
            <div class="details-grid-image agileits w3layouts">
              <img src="/static/images/project-7.jpg" alt="Agileits W3layouts">
            </div>
            <div class="details-grid-info agileits w3layouts">
              <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod	tempor incididunt ut labore et dolore magna aliqua ut enim ad minim veniam.</p>
            </div>
            <button class="btn btn-primary agileits w3layouts wow fadeInLeft" data-toggle="modal" data-target="#myModal3">EXPLORE<span class="glyphicon agileits w3layouts glyphicon-arrow-right" aria-hidden="true"></span></button>
            <div class="clearfix"></div>
          </div>
        </div>
        <div class="clearfix"></div>
      </div>
    </div>
  </div>
</template>

<script>
    export default {
        name: "housecard",
        data: function () {
            return {
                currentDate: new Date()

            }
        }
    }
</script>

<style scoped>
  .time {
    font-size: 13px;
    color: #999;
  }

  .bottom {
    margin-top: 13px;
    line-height: 12px;
  }

  .button {
    padding: 0;
    float: right;
  }

  .image {
    width: 100%;
    display: block;
  }

  .clearfix:before,
  .clearfix:after {
    display: table;
    content: "";
  }

  .clearfix:after {
    clear: both
  }

  #housecard {
    margin-top: 3%;

    padding-left: 1%;
  }
</style>
