<template>
  <div class="app">
    <div class="header">
      <HeaderComponent />
    </div>



    <section class="content">
      <SidebarComponent />
      <div class="main-content">
        <div class="top-section">
          <div class="occupancy">
            <img src="/assets/occupancy.png">
          </div>

          <div class="visitor">

          </div>

          <div class="date">

          </div>

        </div>
      </div>
    </section>


  </div>
</template>



<script>
import HeaderComponent from '@/components/HeaderComponent.vue';
import SidebarComponent from '@/components/SidebarComponent.vue';

export default {
  components: {
    HeaderComponent,
    SidebarComponent
  },
};
</script>

<style>
.date {
  width: 30%;
  height: 78px;
  background: #ffff;
  box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.25);
  border-radius: 10px;
  margin-top: 36px;
}

.visitor {
  margin-right: 36px;
  width: 30%;
  height: 78px;
  background: white;
  box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.25);
  border-radius: 10px;
  margin-top: 36px;
}

.occupancy {
  margin-right: 36px;
  width: 30%;
  height: 78px;
  background: #EE3A43;
  box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.25);
  border-radius: 10px;
  margin-left: 50px;
  margin-top: 36px;
}

.top-section {
  width: 100%;
  display: flex;
}

.main-content {
  z-index: -1;
  position: absolute;
  background: #F5F5F5;
  height: 100vh;
  width: 84.6%;
  right: 0;
  transition: 0.3 ease;
}

.sidebar-menu.close~.main-content {
  width: 100%;
  transition: 0.3 ease;
}



.label {
  font-size: medium;
}
</style>
