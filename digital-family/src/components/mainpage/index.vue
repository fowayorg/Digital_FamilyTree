<template>
  <div class="mainpage clearfix" >
    <div class="header clearfix">
      <div class="title"><i class="el-icon-user"></i><router-link tag="span" :to="{name:'mainInfo'}">族谱管理系统</router-link></div>
      <div class="useredit">
        <ul class="clearfix">
          <li><img src="../../assets/picture/link.jpg" alt="" srcset=""></li>
          <li>
           <el-dropdown>
        <span class="el-dropdown-link">
          admin<i class="el-icon-arrow-down el-icon--right"></i>
        </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item ><span @click="dellogin">退出登录</span></el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
      </li>
        </ul>
      </div>
    </div>
    <div class="leftC part" >
        <el-menu
      default-active="2"
      class="el-menu-vertical-demo"
      @open="handleOpen"
      @close="handleClose"
      background-color="#324157"
      text-color="#fff"
      active-text-color="#ffd04b">
      <el-submenu index="1">
        <template slot="title">
          <i class="el-icon-s-custom"></i>
          <span>族谱管理</span>
        </template>
        <el-menu-item-group>
          <router-link tag='el-menu-item' index="1-1" :to="{name:'familyAdd'}">添加族谱</router-link>
          <router-link tag='el-menu-item' index="1-2" :to="{name:'familyEdit'}">修改族谱</router-link>
          <router-link tag='el-menu-item' index="1-3" :to="{name:'familyDel'}">删除族谱</router-link>
        </el-menu-item-group>
      </el-submenu>
      <el-submenu index="2">
        <template slot="title">
          <i class="el-icon-setting"></i>
          <span>成员管理</span>
        </template>
        <el-menu-item-group>
          <router-link tag='el-menu-item'  :to="{name:'memberAdd'}">添加成员</router-link>
          <router-link tag='el-menu-item' :to="{name:'memberEdit'}">修改成员</router-link>
          <router-link tag='el-menu-item' :to="{name:'memberDel'}">删除成员</router-link>
        </el-menu-item-group>
      </el-submenu>
      <el-submenu index="3">
        <template slot="title">
          <i class="el-icon-share"></i>
          <span>综合管理</span>
        </template>
        <el-menu-item-group>
          <router-link tag='el-menu-item' :to="{name:'searchMember'}">查询成员信息</router-link>
          <router-link tag='el-menu-item' :to="{name:'searchFamily'}">查询指定族谱</router-link>
          <router-link tag='el-menu-item' :to="{name:'searchRelation'}">查询成员亲属</router-link>
          <router-link tag='el-menu-item' :to="{name:'searchTree'}">查询族谱树形图</router-link>
        </el-menu-item-group>
      </el-submenu>
    </el-menu>
    </div>
    <div class="rightC  part" >
      <div class="userinfo">
        <ul>
          <li class="user">
            <div>
                <img src="../../assets/picture/link.jpg" alt="">
            </div>
            <div class="info">
                <p>欢迎您</p>
                <p>超级管理员</p>
                <p>admin</p>
            </div>
            <el-divider></el-divider>
            <div class="qianzi"><i class="el-icon-edit"></i><span>个性签名：</span>世上无难事，只怕有心人</div>
          </li>
        </ul>
      </div>
       <el-divider></el-divider>
       <div class="alledit"><router-view></router-view></div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      url: 'url(' + require('@/assets/picture/img1.png') + ')',
      imgurl: 'url(' + require('@/assets/picture/老八.png') + ')',
      form: {
        name: ''
      },
      activeName: '1'
    }
  },
  methods: {
    handleOpen (key, keyPath) {
      console.log(key, keyPath)
    },
    handleClose (key, keyPath) {
      console.log(key, keyPath)
    },
    dellogin () {
      this.$confirm('确认退出当前账号吗？').then(() => {
        this.$message({
          type: 'success',
          message: '退出成功!'
        })
        this.$router.push({name: 'login'})
      })
    }
  }
}
</script>

<style lang='scss' scoped>
@import "@/assets/css/mainpage.scss";
.el-dropdown-link{
  cursor: pointer;
}
</style>
