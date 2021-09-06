<template>
  <div id="home">
    <nav-bar class="home-nav"><div slot="center">购物街</div> </nav-bar>
    <home-swiper :banners="banners"r></home-swiper>
    <recommend-view :recommends="recommends"></recommend-view>
    <feature-view></feature-view>
    <tab-control :titles="['流行','新款','精选']" class="tab-control"></tab-control>
    <ul>
      <li>libiao1</li>
      <li>libiao2</li>
      <li>libiao3</li>
      <li>libiao4</li>
      <li>libiao5</li>
      <li>libiao6</li>
      <li>libiao7</li>
      <li>libiao8</li>
      <li>libiao9</li>
      <li>libiao10</li>
      <li>libiao11</li>
      <li>libiao12</li>
      <li>libiao13</li>
      <li>libiao14</li>
      <li>libiao15</li>
      <li>libiao16</li>
      <li>libiao17</li>
      <li>libiao18</li>
      <li>libiao19</li>
      <li>libiao20</li>
    </ul>
    <ul>
      <li>liebiao1</li>
      <li>liebiao2</li>
      <li>liebiao3</li>
      <li>liebiao4</li>
      <li>liebiao5</li>
      <li>liebiao6</li>
      <li>liebiao7</li>
      <li>liebiao8</li>
      <li>liebiao9</li>
      <li>liebiao10</li>
      <li>liebiao11</li>
      <li>liebiao12</li>
      <li>liebiao13</li>
      <li>liebiao14</li>
      <li>liebiao15</li>
      <li>liebiao16</li>
      <li>liebiao17</li>
      <li>liebiao18</li>
      <li>liebiao19</li>
      <li>liebiao20</li>
    </ul>

  </div>

</template>

<script>
import NavBar from "@/components/common/navbar/NavBar";
import TabControl from "@/components/condent/tabControl/TabControl";

import HomeSwiper from "@/views/home/childComps/HomeSwiper";
import RecommendView from "@/views/home/childComps/RecommendView";
import FeatureView from "@/views/home/childComps/FeatureView";

import {getHomeMultidata} from "@/network/home";

export default {
  name: "Home",
  data(){
    return{
      banners:[],
      recommends:[]
    }
  },
  components:{
    NavBar,
    HomeSwiper,
    RecommendView,
    FeatureView,
    TabControl
  },

  created() {
    //1.请求多个数据
    getHomeMultidata().then(res=>{
      console.log(res);
      this.banners=res.data.banner.list;
      this.recommends=res.data.recommend.list;
    })
  }
}
</script>

<style scoped>
#home{
  padding-top: 44px;
}
.home-nav{
  background-color: var(--color-tint);
  color: #fff;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  z-index: 9;
 }
.tab-control{
  position: sticky;
  top: 44px;
}
</style>
