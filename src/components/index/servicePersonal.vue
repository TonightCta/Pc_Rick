<template>
  <div class="service-personal w1420">
    <p class="title"><span class="wow xnxg"></span><span class="special-title">人才库</span></p>
    <div class="swiper-container swiper2 p-r">
      <div class="item-content-box swiper-wrapper">
        <div class="item-content f-l clearfix swiper-slide">
          <div class="item-card f-l" v-for="(person,index) in personList">
            <ul>
              <li>
                <img :src="imgUrl+person.icon"/>
                <p class="mark-floor"></p>
              </li>
              <li>
                {{person.name}}
              </li>
              <li>
                {{person.type}}
              </li>
              <li>
                {{person.experience}}
              </li>
              <li>
                {{person.professionType}}
              </li>
              <li>
                <span>联系他</span>
              </li>
            </ul>
          </div>
        </div>
        <div class="item-content f-l clearfix swiper-slide">
          <div class="item-card f-l" v-for="(person,index) in personList2">
            <ul>
              <li>
                <img :src="imgUrl+person.icon"/>
                <p class="mark-floor"></p>
              </li>
              <li>
                {{person.name}}
              </li>
              <li>
                {{person.type}}
              </li>
              <li>
                {{person.experience}}
              </li>
              <li>
                {{person.professionType}}
              </li>
              <li>
                <span>联系他</span>
              </li>
            </ul>
          </div>
        </div>
        <div class="item-content f-l clearfix swiper-slide">
          <div class="item-card f-l" v-for="(person,index) in personList3">
            <ul>
              <li>
                <img :src="imgUrl+person.icon"/>
                <p class="mark-floor"></p>
              </li>
              <li>
                {{person.name}}
              </li>
              <li>
                {{person.type}}
              </li>
              <li>
                {{person.experience}}
              </li>
              <li>
                {{person.professionType}}
              </li>
              <li>
                <span>联系他</span>
              </li>
            </ul>
          </div>
        </div>
        <div class="item-content f-l clearfix swiper-slide">
          <div class="item-card f-l" v-for="(person,index) in personList4">
            <ul>
              <li>
                <img :src="imgUrl+person.icon"/>
                <p class="mark-floor"></p>
              </li>
              <li>
                {{person.name}}
              </li>
              <li>
                {{person.type}}
              </li>
              <li>
                {{person.experience}}
              </li>
              <li>
                {{person.professionType}}
              </li>
              <li>
                <span>联系他</span>
              </li>
            </ul>
          </div>
        </div>
        <div class="item-content f-l clearfix swiper-slide">
          <div class="item-card f-l" v-for="(person,index) in personList5">
            <ul>
              <li>
                <img :src="imgUrl+person.icon"/>
                <p class="mark-floor"></p>
              </li>
              <li>
                {{person.name}}
              </li>
              <li>
                {{person.type}}
              </li>
              <li>
                {{person.experience}}
              </li>
              <li>
                {{person.professionType}}
              </li>
              <li>
                <span>联系他</span>
              </li>
            </ul>
          </div>
        </div>
        <div class="item-content f-l clearfix swiper-slide">
          <div class="item-card f-l" v-for="(person,index) in personList6">
            <ul>
              <li>
                <img :src="imgUrl+person.icon"/>
                <p class="mark-floor"></p>
              </li>
              <li>
                {{person.name}}
              </li>
              <li>
                {{person.type}}
              </li>
              <li>
                {{person.experience}}
              </li>
              <li>
                {{person.professionType}}
              </li>
              <li>
                <span>联系他</span>
              </li>
            </ul>
          </div>
        </div>
      </div>
      <div class="swiper-pagination swiper-p2" style="display: none;"></div>
      <div class="swiper-button-prev" id="prev-btn2"></div>
      <div class="swiper-button-next" id="next-btn2"></div>
    </div>
  </div>
</template>

<script>
    import Swiper from 'swiper'
    export default {
        name: "service-personal",
        data(){
          return {
            imgUrl:"static/images/personImg/",
            personList:[
                {name:"郑彦振",type:"UC，CC，监控",experience:"11年",professionType:"HCNA，HCNP",icon:"person_zyz.png"},
                {name:"耿海涛",type:"UC，CC，监控",experience:"9年",professionType:"HCNA，HCNP",icon:"person_ght.png"},
                {name:"王永胜",type:"系统集成",experience:"17年",professionType:"-",icon:"person_wys.png"},
                {name:"李少华",type:"系统集成",experience:"17年",professionType:"HCNA，HCNP，售前VC",icon:"person_lsh.png"}
              ],
            personList2:[
              {name:"张志伟",type:"IT，数通",experience:"18年",professionType:"-",icon:"person_zzw.png"},
              {name:"腾福庆",type:"能基",experience:"14年",professionType:"-",icon:"person_tfq.png"},
              {name:"孙立业",type:"运维",experience:"14年",professionType:"HCIE",icon:"person_sly.png"},
              {name:"张磊",type:"光伏，VC",experience:"10年",professionType:"-",icon:"person_zl.png"},
            ],
            personList3:[
              {name:"刘鹏",type:"光伏，视讯",experience:"8年",professionType:"HCNP",icon:"person_lp.png"},
              {name:"陈记",type:"视讯",experience:"9年",professionType:"HCNP",icon:"person_cj.png"},
              {name:"杨海光",type:"数通，IT",experience:"7年",professionType:"HCIE",icon:"person_yhg.png"},
              {name:"马东慧",type:"数通，IT",experience:"8年",professionType:"HCNP",icon:"person_mdh.png"},
            ],
            personList4:[
              {name:"凌含涛",type:"数通，IT",experience:"6年",professionType:"HCNP",icon:"person_lht.png"},
              {name:"张立鹏",type:"数通，IT",experience:"5年",professionType:"HCNP",icon:"person_zlp.png"},
              {name:"容雄",type:"数通，IT",experience:"7年",professionType:"HCNP",icon:"person_rx.png"},
              {name:"朱贺真",type:"UC，CC，监控",experience:"5年",professionType:"HCNP",icon:"person_zhz.png"},
            ],
            personList5:[
              {name:"张东磊",type:"UC，CC，监控",experience:"10年",professionType:"HCNP",icon:"person_zdl.png"},
              {name:"于晓东",type:"UC，CC，监控",experience:"9年",professionType:"HCNP",icon:"person_yxd.png"},
              {name:"张陆",type:"UC，CC，监控",experience:"5年",professionType:"HCNP",icon:"person_zl2.png"},
              {name:"赵小林",type:"系统集成",experience:"8年",professionType:"HCNP",icon:"person_zxl.png"},
            ],
            personList6:[
              {name:"罗亮",type:"能基",experience:"9年",professionType:"HCNP",icon:"person_ll.png"},
              {name:"张江林",type:"能基",experience:"10年",professionType:"HCNP",icon:"person_zjl.png"},
            ],
          }
        },
        mounted(){
          new Swiper('.swiper-container .swiper2', {
            autoplay: {
              delay: 3000,
              stopOnLastSlide: false,
              disableOnInteraction: false,
            },
            pagination: {
              el: '.swiper-p2',
              clickable: true,
            },
            navigation: {
              nextEl: '#next-btn2',
              prevEl: '#prev-btn2',
            },
          });
        }
    }
</script>

<style lang="scss" scoped>
  .service-personal{
    height: 800px;
    margin: 0 auto;
    text-align: center;
    .special-title{
      color: $fontColor;
    }
    .xnxg{
      display: inline-block;
      width: 150px;
      height: 55px;
      margin-right: 10px;
      background-size: 100% 100%;
      background-image: url('../../../static/images/xiniuxiaoge.png');
      animation: fadeInLeft 2s;
    }
    .title{
      padding: 30px 0 50px;
      text-align: center;
      font-size: 36px;
      letter-spacing: 2px;
    }
    .swiper-button-prev{
      background: url('../../../static/images/next_icon.png')!important;
      background-size: 100% 100%!important;
      left: 40px;
      transform:rotate(180deg);
    }
    .swiper-button-next{
      background: url('../../../static/images/next_icon.png')!important;
      background-size: 100% 100%!important;
      right: 40px;
    }
  }
  .item-content-box{
    width: 1180px;
    margin: 0 120px;
  }
  .item-content{
    .item-card{
      height: 100%;
      background-size: 100% 100%;
      background-image: url('../../../static/images/contect_msg_home_nor.png');
    }
    .item-card + .item-card{
      margin-left: 20px;
    }
  }
  .item-card{
    width: 280px;
    padding: 0;
    ul{
      width: 280px;
      height: 100%;
      li{
        width:270px;
        margin:0 4px;
        height: 43px;
        text-align: center;
        font-size: 20px;
        line-height: 43px;
        color: #fff;
        &:nth-of-type(2){
          border-top: none;
        }
        &:first-child{
          width:280px;
          position: relative;
          height: 188px;
          /*background-image: url("../../../static/images/enter_im_home_nor.png");*/
          background-color: #000;
          padding-top: 88px;
          margin: 0;
          img{
            position: absolute;
            width: 100%;
            height: 100%;
            left: 0;
            top: 0;
            /*width: 85px;*/
            /*height: 85px;*/
            /*border-radius: 50%;*/
          }
          .mark-floor1{
            position: absolute;
            bottom: 0;
            width: 0;
            height: 0;
            margin: 0;
            border-right: 136px solid $fontColor;
            border-bottom: 50px solid $fontColor;
            border-left: 136px solid transparent;
            border-top: 50px solid transparent;
          }
        }
        &:last-child{
          height: 125px;
          padding-top: 57px;
          span{
            display: block;
            width: 130px;
            height: 47px;
            margin: 0 auto;
            background-size: 100% 100%;
            background-image: url("../../../static/images/contect_btn_home_nor.png");
          }
        }
      }
      li + li{
        border-top: 3px solid #fff;
      }
    }
  }
</style>
