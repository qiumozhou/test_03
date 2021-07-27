<template>
  <div :style="styObj">
    <div class="content">
      <router-link :to="{ path: '/book/index' }">
        <svg-icon iconClass="book_new" class="img-left"></svg-icon>
      </router-link>
      <router-link :to="{ path: '/book/index' }">
        <svg-icon iconClass="phy" class="img-right"></svg-icon>
      </router-link>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "Dashboard",
  data() {
    return {
      styObj: {
        height: 0,
      },
    };
  },
  methods: {
    changeHeight() {
      this.styObj.height = window.innerHeight - 50 + "px";
    },
  },
  mounted() {
    // window.addEventListener('resize', this.changeHeight);
    this.changeHeight();
  },
  computed: {
    ...mapGetters(["name"]),
  },
};
</script>

<style scoped>
.dashboard-container {
  height: auto !important;
  height: 600px;
  min-height: 600px;
}

.content {
  width: 240px;
  height: 120px;
  margin: 0 auto;
  position: relative;
  top: 50%;
  /*偏移*/
  transform: translateY(-100%);
}

.img-left {
  display: inline-block;
  width: 120px;
  height: 120px;
  color: rgb(247, 103, 7);
  background-color: white;
  border-right: crimson 10px solid;
}

.img-left:hover {
  color: white;
  background-color: rgb(247, 103, 7);
  cursor: pointer;
}

.img-right {
  display: inline-block;
  width: 120px;
  height: 120px;
  color: blue;
  background-color: white;
}

.img-right:hover {
  color: white;
  background-color: blue;
  cursor: pointer;
}
</style>
