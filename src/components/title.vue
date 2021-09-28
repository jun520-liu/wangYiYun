<template>
    <div id="app_title">
    <div class="title">
        <!-- 左边的头像 -->
        <div class="head">
            <img src="../assets/A.png" alt="">
        </div>
        <!-- 右边的box -->
        <div class="title_box">
            <div class="box">
                <div class="btn">推荐</div>
                <div class="btn">排行榜</div>
                <div class="btn">歌单</div>
                <div class="btn">主播电台</div>
                <div class="btn">歌手</div>
                <div class="btn">新碟上架</div>
                <!-- 搜索框 -->
                <div class="search">
                    <div class="search_inner">
                       <div><img src="../assets/search.png" alt=""></div>
                       <div><input type="text"></div>
                    </div>
                </div>
                <!-- 更多按钮 -->
                <div class="more">
                       <img @click="title_more_btn" src="../assets/more.png" alt="">
                </div>
            </div>
            <!-- 二级菜单 -->
            <div class="menu" 
            :style="{height:is_hadden==false?'0px':'320px',borderTop:is_hadden==false?'0':'2px solid #ccc'}"
            >
                <div class="sec_btn">推荐</div>
                <div class="sec_btn">排行榜</div>
                <div class="sec_btn">歌单</div>
                <div class="sec_btn">主播电台</div>
                <div class="sec_btn">歌手</div>
                <div class="sec_btn">新碟上架</div>
            </div>
        </div>
    </div>
    <!-- <router-view style="width:100%;height:100%;" class="router"></router-view> -->
  </div>
</template>
<script>
export default {
  name: 'mytitle',
  components: {

  },
  data(){
     return{
          is_hadden:false
     }
  },
  methods:{
    title_more_btn:function(e){
        if(this.is_hadden==false){
            this.is_hadden = true
            return;
        }
        this.is_hadden = false;
    }
  }
}
</script>
<style lang="scss">
#app_title{
   width:100%;
   height:100%;
   .title{
     width:100%;
     height:80px;
     display: flex;

     background-color: #333;
            @media screen and(min-width:1001px) {
                  .menu{
                    display: none !important;
                  }
              }

              @media screen and(max-width:1000px) {

              }

    //  左边的头像
    .head{
        height:80px;
        width:80px;
        display: flex;
        justify-content: center;
        align-items: center;
        img{
           border-radius: 50%;
           width:80%;
           height:80%;
        }
    }
   .title_box{
       height:80px;
       width:1px;
       flex:1;
       display: flex;
       justify-content: flex-end;
       position: relative;
       .box{
              font-size: 1.5rem;
              color:#ccc;
              display: flex;
                justify-content: flex-end;
              @media screen and(min-width:1001px) {
                  .more{
                      display: none !important;
                  }
              }

              @media screen and(max-width:1000px) {
                  .btn{
                      display: none !important;
                  }
              }
              display: flex;
              // justify-content: space-around;
              align-items: center;
              .btn{
                  height:100%;
                  padding-left: 1rem;
                  padding-right: 1rem;
                  display: flex;
                  justify-content: center;
                  align-items: center;
                     cursor: pointer;
                  &:hover{
                    background-color: #000;
                    color:#fff;
                  }
              }
              .search{
                  height:100%;
                  width:15rem; 
                  display: flex;
                  justify-content: center;
                  align-items: center;
                  // 白色背景部分
                  .search_inner{
                      width:80%;
                      height:50%;
                      border-radius: 50px;
                      background-color:#fff;
                      display: flex;
                      justify-content:center;
                      align-items: center;
                      & div:nth-child(1){
                        width:30px;
                        height:30px;
                        img{
                           width:100%;
                           height:100%;
                        }
                      }
                      & div:nth-child(2){
                            width:70%;
                            height:70%;
                            background-color: blue;
                            display: flex;
                            margin-left: 5px;
                            input{
                               width: 100%;
                               height: 100%;
                               border:0;
                               &:focus{
                                 outline: none;
                               }
                            }
                      }
                  }
              }

       }
       //右边的更多
        .more{
        height:80px;
        width:80px;
        display: flex;
        justify-content: center;
        align-items: center;
        img{
           width:40%;
           height:40%;
        }
    }
   }
   
   //二级菜单
   .menu{
     width:150px;
     height:400px;
     background-color:#333;
     position: absolute;
     top:80px;
     right: 0px;
     transition: 0.25s;
     display:flex;
     flex-direction: column;
     overflow: hidden;
     margin-right: 10px;
     .sec_btn{
         width:100%;
         height:50px;
         display: flex;
         justify-content:center;
         align-items: center;
         color:#ccc;
         font-size: 17px;
         cursor: pointer;
         &:hover{
             background-color: #000;
         }
     }
   }


   }
}
</style>