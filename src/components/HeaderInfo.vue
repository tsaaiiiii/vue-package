<template>
  <div class="socialInfo">
    <div class="personalImg">
      <img src="public/images/cat.jpeg" alt="" />
    </div>
    <div class="socialPost">
      <div class="openData">
        <h3>3</h3>
        <h4>貼文</h4>
      </div>
      <div class="openData">
        <h3>100</h3>
        <h4>粉絲</h4>
      </div>
      <div class="openData">
        <h3>209</h3>
        <h4>追蹤中</h4>
      </div>
    </div>
  </div>
  <div class="name">
    <h2>Yvonne</h2>
    <h4>翻譯年糕</h4>
  </div>
  <div class="fixInfo">
    <input type="button" value="編輯個人檔案" />
    <input type="button" value="分享個人檔案" />
    <button @click="showAlert"><span class="material-icons-outlined">group_add</span></button>
  </div>
</template>

<script>
export default {
  methods: {
    showAlert() {
      this.$swal({
        position: 'top-end',
        icon: 'success',
        iconColor: '#3bafe5',
        title: '送出好友邀請',
        showConfirmButton: false,
        timer: 1200,
        width: '260px'
      })
    }
  }
}
</script>

<style scoped>
.socialInfo {
  display: flex;
  gap: 20px;
  justify-content: space-between;
  width: 80%;
}
.name {
  padding-left: 46px;
  padding-top: 5px;
  width: 80%;
}
.personalImg {
  border: solid 1px;
  width: 160px;
  height: 160px;
  border-radius: 100%;
  overflow: hidden;
}
img {
  width: 100%;
  height: 100%;
}
.socialPost {
  width: 60%;
  display: flex;
  justify-content: space-around;
  align-items: center;
  text-align: center;
}
.fixInfo {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin: 30px 10px 20px 0px;
  width: 80%;
}
input {
  width: 250px;
  border: solid 1px #efefef;
  background-color: #efefef;
  border-radius: 5px;
  cursor: pointer;
}
button {
  border: solid 1px #efefef;
  background-color: #efefef;
  border-radius: 5px;
  cursor: pointer;
}
button span {
  font-size: 20px;
}
</style>
