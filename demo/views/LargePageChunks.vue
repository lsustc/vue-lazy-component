<template>
  <div style="height: 100%">
    <div class="index-d3 switch">
      <div class="d3-more" style="display: block">
        <view1 v-if="view1Show" />
        <view2 v-if="view2Show" />
        <view3 v-if="view3Show" />
        <view4 v-if="view4Show" />
        <view5 v-if="view5Show" />
      </div>
    </div>
  </div>
</template>

<script>
import "@/assets/css/common.css";
import "@/assets/css/d3.css";
import "@/assets/css/load.css";
import "@/assets/css/load-sec.css";

export default {
  components: {
    View1(resolve) {
      require(["@/components/View1"], resolve);
    },
    View2(resolve) {
      require(["@/components/View2"], resolve);
    },
    View3(resolve) {
      require(["@/components/View3"], resolve);
    },
    View4(resolve) {
      require(["@/components/View4"], resolve);
    },
    View5(resolve) {
      require(["@/components/View5"], resolve);
    },
  },

  data() {
    return {
      view1Show: false,
      view2Show: false,
      view3Show: false,
      view4Show: false,
      view5Show: false,
    };
  },
  mounted() {
    this.setViewShow();
  },
  methods: {
    setViewShow() {
      setTimeout(() => {
        this.view1Show = true;
        setTimeout(() => {
          this.view2Show = true;
          setTimeout(() => {
            this.view3Show = true;
            setTimeout(() => {
              this.view4Show = true;
              setTimeout(() => {
                this.view5Show = true;
              }, 2000);
            }, 2000);
          }, 2000);
        }, 2000);
      }, 2000);
    },
  },
};
</script>
