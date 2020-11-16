<template>
  <div class="talk__view">
    <div class="top__cover clearfix">
    <div class="content__cover">
      <div class="profile__picture float">
        <img :src="require(`../assets/profile_picture/${user.img}`)" alt="Profile Picture" class="profile__pic">
      </div>

      <div class="float name">
      <span class=" fullname" ><a href="#">{{user.firstName}} {{user.lastName}}</a></span>
      <span class="username">@{{user.username}}</span>
      </div>
    </div >
    </div>
    <div class="message">
      {{talk.content}}
    
    </div>
    
    
  </div>
</template>

<script>
export default {
  name: "TalkView",
  props: {
    talk: {
      type: Object,
      require: true,
    },
    user: {
      type: Object,
      require: true,
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.profile__picture {
  height: 2rem;
  width: 2rem;
  border-radius: 5rem;
  background-color: #aaa;
  overflow: hidden;
}
.profile__pic {
  height:inherit;
  width: inherit;
  background-position: center;
}

.talk__view {
  background-color: #fff;
  margin: 1rem;
  padding: 1.2rem;
  transition: all .3s ease;
  overflow: hidden;
  &:hover {
    transform: translateY(.1rem);
    box-shadow: 0 0 3px .3px;
  }
}
.name {
  line-height: 2rem;
  margin-left: .3rem;
}
.fullname a {
  text-decoration: none;
  color: black;
  font-weight: 600;
  margin-right: .3rem;
}
.username {
  font-size: .7rem;
  color: #abb;
}
.message {
  margin: 1rem 0 0 0;
  overflow: hidden;
  overflow-wrap: break-word;
  font-size: 1.05rem;
  letter-spacing: .03rem;
  width: 100%;
  display: block;
}

</style>
