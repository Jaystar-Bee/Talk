<template>
  <div class="home">
  <div>
    <Header :user="user"/>
  </div>
  <div class="top__cover clearfix">
    <div class="profile__panel">
       <ProfilePanel 
       :user="user" 
       @follow="followIncrease"
       />
       <div v-if="user.admin">
      <CreateTalk
      :talkType="talkType" 
      @submit-text="addTalk"
      />
       </div>        
    </div>

    <div class="talk__panel" >
    <TalkView 
    :talk="talk" 
    v-for="talk in user.talks" 
    :key="talk.id" 
    :user="user"
    />
    </div> 
  </div>
  </div>
</template>

<script>
import Header from "./header";
import ProfilePanel from "./profilePanel";
import { v4 as uuidv4 } from 'uuid';
import TalkView from "./talkView";
import CreateTalk from "./createTalk";

export default {
  name: "TalkPage",
  components: {
    Header,
    ProfilePanel,
    TalkView,
    CreateTalk
  },
  data() {
    return {
      talkType: [
        {value:"draft", name: "Draft"},
        {value:"instant", name: "Instant Talk"},
      ],
      user: {
        id: uuidv4(),
        username: "_Jaystar",
        firstName: "John",
        lastName: "Ayilara",
        email: "amjaystar@gmail.com",
        follower: 0,
        admin: true,
        img: "bodem.jpg",
        talks: [
          {id: uuidv4(),
           content: `Hope am welcome on this platform. `,
          },
          {id: uuidv4(),
           content: `Lets do follow competition, you follow then i follow back instantly, i need new friends on this platform. `,
          }
        ]
      } 
    }
  },
  props: {
  
  },
  methods: {
    followIncrease() {
      this.user.follower++
      alert(`You followed @${this.user.username}`)
    },

    addTalk: function (input, type) {
      if(input && type !== 'draft') {
        this.user.talks.unshift(
          {
            id: uuidv4(),
            content: input
          }
        )
      }
    }
    // addTalk (input, type) {

    //   if (input  && type !== draft) {
    //     this.talks.unshift(
    //       {
    //         id: uuidv4(),
    //         content: input,
    //       }
    //     )
    //   }
    // }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.top__cover {
  margin: 0 auto;
  width: 90%;
}
.profile__panel {
  float: left;
}
.talk__panel {
  width: 60%;
  max-width: 50rem;
  float: left;
}
.clearfix{
  content: "";
  display: table;
  clear: both;
}
.talk__panel {
  background-color:  rgba(255, 255, 255, 0.3);
  border-radius: .3rem;
  margin: 2rem 0;
}

</style>
