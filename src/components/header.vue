<template>
  <div class="header clearfix">
      <h1 class="header__name float">Talk Now</h1>

      <p class="header__username float">@{{user.username}}</p>
      
    
  </div>
</template>

<script>
export default {
  name: "Header",
  props: {
      user: {
          type:Object,
          require: true,
      }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header {
    background-image: linear-gradient(to right, rgba(255, 255, 255, 0.3), rgba(255, 255, 255, 0.3) );
    padding: 1rem;
    transition: all .4s ease;
    position: relative;
    width: 100%;
    width: vw;

    &:hover {
        background-image: linear-gradient(to right bottom, rgba(16, 46, 102, .3) , rgba(47, 100, 96, .3));
        box-shadow: 0 0 .2rem .2rem rgb(0, 0, 0);
        color: white;
        backface-visibility: hidden;
        -webkit-backface-visibility: hidden;
    }

  .header__Name {

}
  .header__username {
      position: absolute;
      top: .2rem;
      right: .5rem;
      line-height: 4rem;
    }
}


</style>
