<template>
  <div class="create__talk">
      <div class="create__cover"> 
          <h4 class="heading">Create Talk <span>({{characterCount}}/250)</span></h4>

          <form @submit.prevent="submit">
          <textarea id="input" rows="3" v-model="input" cols="3" maxlength="250"></textarea>

          <div>
              <label for="type" class="type">Type:</label>
              <select id="type" v-model="type" max-length= "200"> 
                <option :value="option.value"
                v-for="(option, index) in talkType" :key="index">
                      {{option.name}}     
                </option>

              </select>
          </div>
          <button class="submit">Talk!</button>

          </form>
      </div>
    
  </div>
</template>

<script>

export default {

    name: "CreateTalk",
    data() {
        return {
            input: "",
            type: "instant"
        }       
    },

    props: {
        talkType: {
            type: Object,
            require: true,
        }
            

    },
    computed: {
        characterCount () {
        return this.input.length
        }
    },

    methods: {
        submit() {

            this.$emit('submit-text', this.input, this.type); 
            this.input="";
        }
    },
    
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.create__talk {
 margin: 2rem;
 background-color: rgba(255, 255, 255, 0.3);
 border-radius: .3rem;
 padding: .7rem;
}
.create__cover {
    background-color: #fff;
    padding: .7rem;
}
.heading {
    color:rgb(16, 46, 102);
    margin: .5rem 0;
}
textarea {
    resize: none;
    width: 100%;
    padding: .4rem;
    font-size: 1.2rem;

    &:focus {
        outline: none;
    }
}
.type {
    font-size: .8rem;
    font-weight: 700;
}
#type {
    border: none;
    outline: none;
    margin-left: .5rem;
    backface-visibility: hidden;
    &:hover, :focus, :visited {
        border: none;
        outline: none;
        
    }
}
.submit {
    margin:1rem 0;
    padding: .2rem 1rem;
    border: none;
    background-color: rgb(16, 46, 102);
    color: #fff;
    &:hover, :focus, :visited{
        border: none;
        outline: none;
        
    }
}
</style>
