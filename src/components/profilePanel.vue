<template>
  <div class="profile__panel-cover"> 
      <div class="profile__panel">
          <div class="profile__picture">
              <img :src="require(`../assets/profile_picture/${user.img}`)" alt="Profile Picture" class="profile__pic">
          </div>
          <h1 class="Profile__panel-name">{{ user.firstName}} {{user.lastName}}</h1> <span class="username">@{{ user.username }}</span>
          <div class="profile__panel-followers">followers <span class="follower__number">{{ user.follower }}</span></div>
        <div class="isadmin" v-if="user.admin">Admin</div>
      
        <button class="btn follow__btn" v-if="!user.admin" @click="$emit('follow')">follow</button>
     </div>
  </div>
</template>

<script>

export default {
  name: "ProfilePanel",
  props: {
      user: {
          type: Object,
          require: true,
      },
      image: {
          type:String,
          require: true
      }
  },

//   mounted() {
//       this.$refs.profilePic.style.backgroundImage = "url(user.img)";
//   },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.profile__panel-cover {
 margin: 2rem;
 background-color: rgba(255, 255, 255, 0.3);
 border-radius: .3rem;
 padding: .7rem;
 width: fit-content;
 backface-visibility: hidden;
 transition: transform .4s ease;
 &:hover {
     transform: translateY(.1rem);
 }
}
.profile__panel {
    background-color: #fff;
    padding: 1rem;
    width: inherit;
}
.profile__picture {
    height: 3rem;
    width: 3rem;
    border-radius: 5rem;
    background-color: #aaa;
    overflow: hidden;
    margin-bottom: .5rem;
}
.profile__pic {
    height:inherit;
    width: inherit;
    background-position: center;
}
.Profile__panel-name {
    font-size: 1.2rem;
    display: inline;
}
.username {
    font-size: .7rem;
    color: grey;
    
}
.isadmin {

    background-color: rgb(16, 46, 102);
    width: fit-content;
    padding: .3rem;
    font-size: .8rem;
    color: #fff;
    margin: .3rem 0;
    display: inline;
    // border-top-left-radius: .2rem;
    // border-bottom-left-radius: .2rem;

}
.profile__panel-followers {
    font-weight: 400;
    font-size: .9rem;
    margin: .3rem 0;
}
.follow__btn {

    padding: .3rem;
    margin-top: .3rem;
    border: none;
    outline: none;
    cursor: pointer;
    font-size: .8rem;
    background-color: #ccc;
    // border-top-right-radius: .2rem;
    // border-bottom-right-radius: .2rem;
 &:hover, :visited, :focus{
    outline: none;
    border: none;
    background-color: #aaa;
}
}
</style>
