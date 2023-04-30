<template>
  <div class="footerPost">
    <div class="postSelectBtn">
      <span class="material-symbols-outlined">view_module</span>
      <span class="material-symbols-outlined">perm_contact_calendar</span>
    </div>
    <div class="post">
      <div class="postcontent" v-for="(item, index) in photo" :key="index">
        <div class="postTitle">
          <div class="myPic">
            <img src="@/assets/images/cat.jpeg" alt="" />
          </div>
          <h4>Yvoo_eeeee</h4>
        </div>
        <div class="postImg">
          <img :src="imagePaths[item.img]" alt="" />
        </div>
        <div class="postIcons">
          <div class="postIconsLeft">
            <span class="material-symbols-outlined favorite" @click="favoriteAlert">favorite</span>
            <span class="material-symbols-outlined" @click="messageAlert"> maps_ugc </span>
            <span class="material-symbols-outlined" @click="sendAlert">schedule_send</span>
          </div>
          <div>
            <span class="material-symbols-outlined" @click="collectAlert">bookmark</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import post1 from '@/assets/images/post1.jpg'
import post2 from '@/assets/images/post2.png'
import post3 from '@/assets/images/post3.png'
export default {
  methods: {
    favoriteAlert() {
      this.$swal({
        position: 'top-end',
        icon: 'success',
        iconColor: '#F08080',
        title: '點擊喜歡',
        showConfirmButton: false,
        timer: 1500,
        width: '300px'
      })
    },
    messageAlert() {
      this.$swal('已將訊息傳送', '', 'Success')
    },
    sendAlert() {
      this.$swal({
        title: '分享貼文',
        text: '給你所有的朋友',
        icon: 'Info',
        showCancelButton: true,
        confirmButtonColor: '#3085d6',
        cancelButtonColor: '#d33',
        confirmButtonText: 'OK!OK!',
        cancelButtonText: '再想想'
      }).then((result) => {
        // console.log(result);
        if (result.isConfirmed) {
          this.$swal('已分享', '可以開始討論貼文內容～', 'success')
        }
      })
    },
    collectAlert() {
      this.$swal({
        position: 'top-end',
        icon: 'success',
        iconColor: '#3bafe5',
        title: '儲存成功',
        showConfirmButton: false,
        timer: 1500,
        width: '300px'
      })
    }
  },
  data() {
    return {
      imagePaths: {
        'post1.jpg': post1,
        'post2.png': post2,
        'post3.png': post3
      },
      photo: [
        {
          img: 'post1.jpg'
        },
        {
          img: 'post2.png'
        },
        {
          img: 'post3.png'
        }
      ]
    }
  }
}
</script>

<style scoped>
.footerPost {
  margin-top: 150px;
}
.postSelectBtn {
  display: flex;
  margin-top: 100px;
  border-bottom: solid 1px #efefef;
  padding-bottom: 10px;
  z-index: -100;
}
.postSelectBtn span {
  font-size: 48px;
  width: 50%;
  text-align: center;
  cursor: pointer;
}
.post {
  display: flex;
  margin-top: 50px;
}
.postcontent {
  width: 33.33%;
}
.postTitle {
  display: flex;
  gap: 12px;
}
.myPic {
  border: solid 1px #efefef;
  width: 40px;
  height: 40px;
  border-radius: 100%;
  overflow: hidden;
}
.myPic img {
  width: 100%;
  height: 100%;
}
h4 {
  display: flex;
  align-items: center;
}
.postImg {
  margin-top: 10px;
  width: 100%;
}
.postImg img {
  height: 450px;
  width: 100%;
}
.postIcons {
  display: flex;
  justify-content: space-between;
  padding: 0px 28px 0px 12px;
  align-items: center;
}
.postIcons span {
  font-size: 28px;
  cursor: pointer;
}
.postIconsLeft {
  display: flex;
  gap: 5px;
  align-items: center;
}
.material-symbols-outlined.favorite {
  padding-top: 3px;
}
</style>
