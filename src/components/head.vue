<template>
  <div class="header-card">
    <el-row>
      <el-col :span="24">
        <div class="header-box">
          <div class="ht-nav clearfix">
            <!-- logo -->
            <div class="ht-logo f-l">
              <img src="../../static/images/tab_logo_home_nor.png" width="334" height="51">
            </div>
            <!-- 首页导航 -->
            <ul class="nav f-l clearfix">
              <li>
                <router-link :to="{name:'index'}" :class="{'active':activeArr[0]}" @click.native="changeTab(0)">
                  首页
                </router-link>
              </li>
              <li>
                <router-link :to="{name:'aboutUs'}" :class="{'active':activeArr[1]}" @click.native="changeTab(1)">关于我们</router-link>
              </li>
              <!-- <li> -->
                <!-- <router-link :to="{name:'servicePlatformView'}"  :class="{'active':activeArr[2]}" @click.native="changeTab(2)">犀牛小哥平台</router-link> -->
                <!-- <a href="http://www.rightservicetech.com:8080/index" target="_blank">犀牛小哥平台</a> -->
              <!-- </li> -->
              <li>
                <router-link :to="{name:'PlanPro'}" :class="{'active':activeArr[2]}" @click.native="changeTab(2)">产品与解决方案</router-link>
              </li>
              <li>
                <router-link :to="{name:'successfulCaseView'}" :class="{'active':activeArr[3]}" @click.native="changeTab(3)">成功案例</router-link>
              </li>
              <li>
                <router-link :to="{name:'newsView'}" :class="{'active':activeArr[4]}" @click.native="changeTab(4)">新闻中心</router-link>
              </li>
              <!-- <li> -->
                <!-- <router-link :to="{name:'contactUs'}" :class="{'active':activeArr[5]}" @click.native="changeTab(5)">联系我们</router-link> -->
              <!-- </li> -->
            </ul>
          </div>
          <p class="header_oper" v-show="isLogin">
            <span class="oper_box">
              <router-link :to="{name:'engineer'}" tag="span" @click.native="changeTab(6)">注册</router-link>
              <span>|</span>
              <router-link :to="{name:'LoginIn'}" tag="span" @click.native="changeTab(6)">登录</router-link>
            </span>
          </p>
          <p v-show="hasLogin">
            欢迎您，<span style="color:#eb7a1d;cursor:pointer;" @click="comeMine()">{{userMes.nickname}}</span>(
            <span style="cursor:pointer;text-decoration:underline;color:#eb7a1d;" @click="loginOut()">退出</span>)
          </p>
          <!-- <p class="admin" @click="admin">Admin</p> -->
          <!-- <img :src="doll" alt="" class="header-doll"> -->
          <Mas/>
        </div>
      </el-col>
    </el-row>

  </div>
</template>

<script>
  import bus from "../assets/eventBus"
  import Mas from '@/components/mascot'
  import {mapState,mapMutations} from 'vuex'
  export default {
    name: 'head-nav',
    inject:['reload'],
    data () {
      return {
        activeArr:[true],
        doll:'/static/images/right_doll.png',
        isLogin:true,//是否登录
        hasLogin:false,//已登录
        userMes:{}
      }
    },
    components:{
      Mas
    },
    computed:{
      // ...mapState(['userMes'])
    },
    mounted(){
      if(window.sessionStorage.getItem('user')){
        this.userMes=JSON.parse(window.sessionStorage.getItem('user'));
      }
      var that = this;
      bus.$on("clickChannel",function (activeArr) {
        that.activeArr = activeArr;
      });
      if(that.userMes.nickname){
        that.isLogin=false;
        that.hasLogin=true;
      }else{
        that.isLogin=true;
        that.hasLogin=false;
      }
    },
    methods:{
      ...mapMutations(['userMes_fn']),
      comeMine(){//跳转个人中心
        if(this.userMes.identityCode==3){
          this.$router.push('/companyMine');
        }else{
          this.$router.push('/mine');
        }
        this.changeTab(6)
      },
      changeTab(num){
        for(var i=0;i<this.activeArr.length;i++){
          if(i!=num)
            this.$set(this.activeArr,i,false);
        }
        this.$set(this.activeArr,num,true);
      },
      loginOut(){//注销登录
        this.userMes_fn('');
        window.sessionStorage.clear('user')
        this.isLogin=true;
        this.hasLogin=false;
        this.$router.push('/')
      },
      // admin(){
      //   this.$router.push('/admin')
      // }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  .header-card{
    width: 100%;
    position: fixed;
    left:0;
    top: 0;
    z-index: 6666;
    background-color: #fff;
    height: 111px;
    overflow: hidden;
    box-shadow: 0px 0px 10px #999;
  }
  .header-box{
    // background: red;
    margin: 0 auto;
    background-color: #fff;
    .header_oper{
      height: 111px;
      width: 100%;
      .oper_box{
        display: inline-block;
        width: 90px;
        text-align: center;
        span{
          cursor:pointer;
        }
      }
    }
    .admin{
      color:#eb7a1d;
      position: absolute;
      right:300px;
      top:30px;
      cursor:pointer;
      text-decoration:underline;
    }
  }
  .ht-nav{
    height: 51px;
    margin: 0 auto;
    padding: 30px 0;
    width: 1420px;
    .ht-logo{
      margin-left: 30px;
    }
    .nav {
      margin-left:300px;
      li{
        height: 51px;
      }
      a{
        display: block;
        color: #202020;
        font-size: 18px;
        font-weight: bold;
        padding:2px 5px;
        margin-top: 25px;
        background-color: transparent;
      }
      li:nth-child(1){
        margin-left: 50px;
      }
      li + li{
        margin-left: 50px;
      }
      .active{
        color: $fontColor;
      }
    }
  }
</style>
