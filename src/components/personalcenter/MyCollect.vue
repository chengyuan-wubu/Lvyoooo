<template>
<div>
  <ul class="myfocus container-fluid">
    <li class="nav navbar navbar-nav col-md-4  card">
      <div class="col-md-12  margin icno">
        <div class="row">
          <div class="col-md-3"></div>
          <div class="focus-icon col-md-6  "><a href="####"><img class="img-circle" src="http://n3-q.mafengwo.net/s10/M00/0F/9B/wKgBZ1iUpFWAbScxAAC2Vfg46fo14.jpeg?imageMogr2%2Fthumbnail%2F%21200x200r%2Fgravity%2FCenter%2Fcrop%2F%21200x200%2Fquality%2F90" height="80" width="80"></a></div>
          <div class="col-md-3"></div>
        </div>
      </div>
      <div class="name col-md-12">旧时心语</div>
      <div class="hei col-md-12 margin">
        <div class="col-md-3 nopadding"><p>10</p><a href="####">粉丝</a></div>
        <div class="col-md-6 nopadding"><p>2345</p><a href="####">游记</a></div>
        <div class="col-md-3 nopadding"><p>23</p><a href="####">攻略</a></div>
      </div>
      <div class="col-md-12 anniu">
        <div class="btn  col-md-5 cancel">取消关注</div>

        <div class="btn  col-md-5 message">私信</div>
      </div>
    </li>
    <li class="nav navbar navbar-nav col-md-4"></li>
    <li class="nav navbar navbar-nav col-md-4"></li>
  </ul>
</div>

</template>

<!--复制模板-->

<script>
export default {
  name: 'MyCollect',
  // props:['user'],
  data () {
    return {

    }
  },
  created(){

    // this.props.user = this.user

    // this.props.token = "123"
},

  method:{

    // 获取关注人信息
    getmessage:function () {
      var vm  = this
      var id = sessionStorage.getItem("id")
      axios.get(' http://127.0.0.1:8000/user/myfocus/' + id + '/')
        .then(function (response) {
          vm.some = response.data
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
  /*默认显示*/
  ul,li{
    list-style: none;
  }
  .icno{
    background-color: rgba(169, 169, 169, 0.31);
  }
  .myfocus {
    width: 100%;
    height: 100%;
    align-items: center;
  }
  .card{
    border: rgba(0, 0, 0, 0.2) 1px solid;
    border-radius: 10px;
    box-shadow: rgba(0, 0, 0, 0.2) 0px 1px 10px 1px ;
    padding: 10px 15px;
  }
  .name{
    width: 100%;
    text-align: center;
    height: 20px;
    font-size: 20px;
    font-weight: bold;
    margin: 10px auto;
  }
  .nopadding{
    padding: 0px !important;
  }
  .hei{
    text-align: center;
  }
  p{
    font-weight: bolder;
    margin-bottom: 0px;

  }
  a{
    font-weight: bold;
  }
  .cancel{
    background-color: darkgrey;
    text-align: center;
    padding: 0px;
    height: 34px;
    line-height: 32px;


  }
  .message{
    border:1px solid limegreen;
    color: limegreen;
    margin-left: 29.875px;
  }
  .message:hover{
    color: white;
    background-color: limegreen;
    transition: background-color 0.2s, color 0.3s;
  }
  .anniu{
    margin: 10px 0px;
  }
</style>
