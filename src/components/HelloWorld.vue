
<template id="title1">
  <div>
  <div class="nav navbar navigation navbar-default title1">
    <div class="container">
      <a href="####" class="col-md-2 nav navbar-header logo"><img src="../assets/images/logo.png" alt=""></a>
      <ul class="col-md-4 nav navbar-nav">
        <li><a href="####">首页</a></li>
        <li><a href="####">攻略</a></li>
        <li><a href="####">游记</a></li>
      </ul>
      <ul class="col-md-2 nav navbar-nav navbar-right" v-if="true">
        <li>
          <router-link to="/login"><a href="####">登录</a></router-link>
        </li>
        <li>
          <router-link to="/regist"><a href="####">注册</a></router-link>
        </li>
      </ul>
      <div v-if="aa">
      <div class="col-md-1"></div>
      <ul class="col-md-2 nav navbar navbar-right usericno " v-if = 'false'>
        <li ><router-link to="/usercenter"><a href="####"><img class="img-circle icno col-md-6"
                                src="http://n2-q.mafengwo.net/s10/M00/6C/09/wKgBZ1nm_RuAcRY4AABeA1K-J9Y49.jpeg?imageMogr2%2Fthumbnail%2F%21200x200r%2Fgravity%2FCenter%2Fcrop%2F%21200x200%2Fquality%2F90"
                                alt=""><span class="left col-md-6">棕色试剂瓶</span></a></router-link></li>
      </ul>
      <ul class="col-md-2 nav navbar navbar-right droplist">
        <li class="switch"></li>
        <li><a href="####">我的关注</a></li>
        <li><a href="####">我的收藏</a></li>
        <li><a href="####">我的游记</a></li>
        <li><a href="####">我的攻略</a></li>
        <li><a href="####">写游记</a></li>
        <li><a href="####">写攻略</a></li>
        <li><a href="javascript:;" class="exit">退出</a></li>
      </ul>
      </div>
    </div>
  </div>
  <lunbotu></lunbotu>
  <contentleft></contentleft>
  <contentright></contentright>
  <footer></footer>
  </div>


</template>
<!--复制模板-->

<script>
  import axios from 'axios'
export default {
  name: 'HelloWorld',
  // props:['user'],
  data () {
    return {
      id:1,
      aa:1,
      bb:0,
      props:["user","token"],
      user:{
        'id':'1',
        "username":"棕色试剂瓶",
        "usericno":"http://n3-q.mafengwo.net/s10/M00/0F/9B/wKgBZ1iUpFWAbScxAAC2Vfg46fo14.jpeg?imageMogr2%2Fthumbnail%2F%21200x200r%2Fgravity%2FCenter%2Fcrop%2F%21200x200%2Fquality%2F90",
        "sex":"男",
        "mark":"15",
        "birthday":"1997-6-2",
        "state":"大庆",
        "content":"起始",
      },
      msg: 'Welcome to Your Vue.js App'
    }
  },
  created(){
    sessionStorage.setItem("token","congqianyouzuoshan")
    sessionStorage.setItem("id","1")
    this.token = "gzw"
    console.log(this.props)
},

  method:{
    // 显示热门游记
    showtrvelnotes:function () {
      var vm  = this
      axios.get(' http://127.0.0.1:8000/user/myfocusnum/' + vm.user.id + '/')
        .then(function (response) {
          // vm.some = response.data
          // alert(vm.some)
          // 获取所有数据
          // vm.alldata = response.data
        })
        .catch(function (error) {
          return error
        })
    }
  }
}
</script>
<style scoped>
  .title1 {
    height: 54px;
    background-color: #333333 !important;
    background-image: none !important;
    border: none !important;
    margin-bottom: 0 !important;
    color: whitesmoke !important;
    border-radius: 0px !important;
    /*display: none;*/
  }
  .sowingmap #searchbox{
    width: 300px!important;
    height: 60px!important;
    background-color: rgb(14, 0, 6) !important;
    /*filter: alpha(opacity=50);*/
    position: absolute!important;
    top: 500px!important;
    left: 500px!important;
    /*font-size: 14px;*/
    /*color: whitesmoke;*/
    z-index: 10!important;
    /*transition: height 0.1s;*/
    border-radius: 4px;
  }
  .search{
    height: 60px;
    width: 100%;
    border: whitesmoke 1px solid;
    border-radius: 5px;
  }
  .title1 a {
    color: whitesmoke !important;
    font-size: 15px !important;
  }

  .title1 a:hover {
    color: lawngreen !important;

    transition: color 0.2s;
  }

  .usericno {
    margin: 0;
    height: 54px;
    width: 200px;
  }

  .usericno .icno {
    height: 45px !important;
    width: 45px !important;
    padding: 0;
    margin-top: 5px;
    background-image: url("http://n2-q.mafengwo.net/s10/M00/6C/09/wKgBZ1nm_RuAcRY4AABeA1K-J9Y49.jpeg?imageMogr2%2Fthumbnail%2F%21200x200r%2Fgravity%2FCenter%2Fcrop%2F%21200x200%2Fquality%2F90");
    object-fit: cover;
    vertical-align: center;
  }

  .username {
    font-size: small !important;
    line-height: 54px;
    vertical-align: center;
  }

  .usermessage {
    display: none;
    border-radius: 4px;
    min-height: 500px;
    width: 100%;
    background-color: yellowgreen;
  }
  .notes-del-confirm {
    width: 480px;
    text-align: center;
    position: fixed;
    left: 50%;
    top: 50%;
    z-index: 501;
    margin: -130px 0px 0px -240px;
  }
  .notes-del-confirm{
    width: 480px;
    text-align: center;
    position: fixed;
    left: 50%;
    top: 50%;
    z-index: 501;
    margin: -130px 0px 0px -240px;
  }
  /*title2*/

  .title2{
    box-shadow: rgba(0, 0, 0, 0.25) 1px 1px 5px 3px;
    /*display: none;*/
  }
  .title2-left li:active{
    background-color: rgba(76, 174, 76, 0.75) !important;
    transition: background-color 0.3s;
    color: whitesmoke;
  }

  .usericno .icno {
    height: 45px !important;
    width: 45px !important;
    padding: 0;
    margin-top: 5px;
    background-image: url("http://n2-q.mafengwo.net/s10/M00/6C/09/wKgBZ1nm_RuAcRY4AABeA1K-J9Y49.jpeg?imageMogr2%2Fthumbnail%2F%21200x200r%2Fgravity%2FCenter%2Fcrop%2F%21200x200%2Fquality%2F90");
    object-fit: cover;
    vertical-align: center;
  }

  .usericno li a:hover {
    background-color: rgba(250, 0, 255, 0) !important;
  }

  .usericno li {
    height: 54px;
  }

  .usericno li a {
    height: 53px;
    padding: 0 !important;
    vertical-align: center;
  }

  .usericno li a span {
    height: 53px;
    color: #222222;
    line-height: 54px;
    font-size: small;
    padding-left: 10px;
    padding-right: 0;
  }

  .usericno {
    margin: 0;
    height: 54px;
    width: 190px;
  }
  .nologin{
    display: none;
  }

  .usericno:hover + .droplist {
    display: block !important;
  }

  .droplist {
    display: none;
    padding: 0;
    color: #222222 !important;
    border-radius: 5px;
    width: 150px!important;
    position: absolute;
    left: 1052px;
    top: 53px;
    z-index: 3;
    background-color: rgba(250, 251, 255, 0.82);
  }
  .droplist li a{
    color:black!important;
  }
  .droplist .switch {
    height: 5px;
    opacity: 0;
  }

  .droplist:hover {
    display: block;
    z-index: 10!important;
  }

</style>
