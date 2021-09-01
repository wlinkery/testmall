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
      <li>ll1</li>
      <li>ll2</li>
      <li>ll3</li>
      <li>ll4</li>
      <li>ll5</li>
      <li>ll6</li>
      <li>ll7</li>
      <li>ll8</li>
      <li>ll9</li>
      <li>ll10</li>
      <li>ll11</li>
      <li>ll12</li>
      <li>ll13</li>
      <li>ll14</li>
      <li>ll15</li>
      <li>ll16</li>
      <li>ll17</li>
      <li>ll18</li>
      <li>ll19</li>
      <li>ll20</li>
      <li>ll21</li>
      <li>ll22</li>
      <li>ll23</li>
      <li>ll24</li>
      <li>ll25</li>
      <li>ll26</li>
      <li>ll27</li>
      <li>ll28</li>
      <li>ll29</li>
      <li>ll30</li>
      <li>ll31</li>
      <li>ll32</li>
      <li>ll33</li>
      <li>ll34</li>
      <li>ll35</li>
      <li>ll36</li>
      <li>ll37</li>
      <li>ll38</li>
      <li>ll39</li>
      <li>ll40</li>
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
