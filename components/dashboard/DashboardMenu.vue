<template>
  <div>
    <div :class="toggleMenu ? 'menu' : 'menu-min'">
     
      <div :class="toggleMenu ? 'dashboard-title' : 'dashboard-title-min'">
        <!-- <menu-item heading="Dashboard" iconType="fab fa-dyalog" :max="toggleMenu " >
         
         </menu-item> -->
        <i class="fab fa-dochub"></i> <span>Dashboard</span>
      </div>
      <div>
        <menu-item
          heading="Overview"
          iconType="fas fa-chart-pie"
          :max="toggleMenu"
        >
        </menu-item>

        <menu-sab-item
          heading="Bookings"
          iconType="fas fa-ticket-alt"
          :max="toggleMenu"
        >
          <menu-item heading="All order" />
          <menu-item heading="Create Order" />
        </menu-sab-item>

        <menu-sab-item
          heading="Employement"
          iconType="fas fa-users"
          :max="toggleMenu"
        >
          <menu-item heading="Internship" />
          <menu-item heading="Employee" />
        </menu-sab-item>
        <menu-sab-item heading="Users" iconType="fas fa-user" :max="toggleMenu">
          <menu-sab-item heading="Customer" sub="true">
            <menu-item heading="Onboard" />
            <menu-item heading="View / Edit" />
            <menu-item heading="Block" />
          </menu-sab-item>

          <menu-sab-item heading="Partners" sub="true">
            <menu-item heading="Onboard" />
            <menu-item heading="View Profile" />
            <menu-item heading="Block" />
          </menu-sab-item>
          <menu-sab-item heading="Event Logs" sub="true">
            <menu-item heading="Customer" />
            <menu-item heading="Partner" />
            <menu-item heading="Team" />
          </menu-sab-item>
          <menu-sab-item heading="Location" sub="true">
            <menu-item heading="Customer" />
            <menu-item heading="Partner" />
            <menu-item heading="Team" />
          </menu-sab-item>
        </menu-sab-item>
        <menu-sab-item
          heading="Application Data"
          iconType="fas fa-book"
          :max="toggleMenu"
        >
          <menu-item heading="Images" />
          <menu-item heading="Blog" />
        </menu-sab-item>
        <menu-sab-item
          heading="Service Data"
          iconType="fas fa-shapes"
          :max="toggleMenu"
        >
          <menu-item heading="Rates" />
          <menu-item heading="Contents" />
        </menu-sab-item>

        <menu-sab-item
          heading="Revenue"
          iconType="fas fa-money-bill"
          :max="toggleMenu"
        >
          <menu-item heading="Earning" />
          <menu-item heading="Expences" />
        </menu-sab-item>
        <hr />
        <!-- <menu-sab-item heading="Offers & Promocodes" iconType="fas fa-tag" :max="toggleMenu " >
           <menu-item heading="View Promocodes" />
           <menu-item heading="Create Promocodes" />
      </menu-sab-item> -->

        <menu-sab-item
          heading="Settings"
          iconType="fas fa-cog"
          :max="toggleMenu"
          class="setting"
        >
          <menu-item heading="User Access" />
          <menu-item heading="Logout" />
        </menu-sab-item>
        <hr />
      </div>
      <div @click="toggle()">
        <!-- <i class="fas fa-angle-right toggle-icon" v-show="icon1" @click="toggle()" ></i> 
            <i class="fas fa-angle-left toggle-icon" v-show="icon2" @click="toggle()"></i> -->
        <menu-item
          class="menu-toggle"
          iconType="fas fa-angle-right "
          v-show="icon1"
        />
        <menu-item
          class="menu-toggle"
          iconType="fas fa-angle-left"
          v-show="icon2"
        />
      </div>
    </div>
  </div>
</template>
<style scoped>
.menu {
  display: flex;
  flex-direction: column;
  width: 265px;
  box-sizing: border-box;

  min-height: 100vh;
  height: auto;
  background-color: #363740;
  color: #9fa2b4;
  transition: width 0.5s ease;
}
.menu-min {
  display: flex;
  flex-direction: column;
  width: 100px;
  background-color: #363740;
  color: #9fa2b4;
  box-sizing: border-box;

  min-height: 100vh;
  height: auto;
  transition: width 0.5s ease;
}
.setting {
  margin: 56px 0px;
}
hr {
  margin-top: -2px;
  border-top: 2px solid #9fa2b4;
}
.menu-toggle {
  float: right;
}
.toggle-icon {
  height: 10px;
}
/*  */
.dashboard-title {
  height: 80px;
  margin: 20px 40px;
  font-size: 22px;
  color: #3751ff;
}
.dashboard-title-min {
  height: 80px;
  margin: 20px 40px;
  font-size: 22px;
  color: #3751ff;
}
.dashboard-title-min span {
  display: none;
}
.dashboard-title span {
  color: #9fa2b4;
}
</style>

<script>
import menuItem from "./menu-item.vue";
import MenuSabItem from "./menu-sab-item.vue";

export default {
  components: { menuItem, MenuSabItem },
  data() {
    return {
      toggleMenu: true,
      icon1: true,
      icon2: false,
    };
  },
  methods: {
    menuToggle() {},
    toggle() {
      this.icon1 = !this.icon1;
      this.icon2 = !this.icon2;
      this.toggleMenu = !this.toggleMenu;
    },
  },
};
</script>
