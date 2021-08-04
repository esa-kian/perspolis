<template>
    <div class="post" :id="'post'+post.id">
        <div class="header">
            <div class="user">
                <div class="avatar">
                    <img :src="post.user.avatar" width="44" height="44" alt="">
                </div>
                <div class="username">{{post.user.username}}</div>
            </div>
            <div class="star">
                <v-btn x-small icon light color="pink">
                    <v-icon>mdi-star</v-icon>
                </v-btn>
                 <v-btn x-small icon light color="pink">
                    <v-icon>mdi-star</v-icon>
                </v-btn>
                 <v-btn x-small icon light color="pink">
                    <v-icon>mdi-star</v-icon>
                </v-btn>
                 <v-btn x-small icon light color="pink">
                    <v-icon>mdi-star</v-icon>
                </v-btn>
                 <v-btn x-small icon light color="pink">
                    <v-icon>mdi-star</v-icon>
                </v-btn>
                {{ post.rate }}
                <div @click="close" v-if="show_more" class="close">
                    <v-icon>mdi-close</v-icon>
                </div>
            </div>
        </div>
        <div class="body">
            <div class="photo">
                <img :src="post.image" alt="">
            </div>
            <div class="caption">{{!show_more ? post.caption.substring(0,100) : post.caption }} 
                <span v-if="!show_more" @click="more">{{(post.caption.length>100?'...More':'')}}</span>
            </div>
        </div>
        <div class="footer">
            <div class="comments">
                <div @click="show_comments = !show_comments" v-if="post.comments.length" class="title">
                    <v-btn x-small icon light color="pink">
                        <v-icon>mdi-comment</v-icon>
                    </v-btn>
                    <span>
                        COMMENTS {{'('+post.comments.length+')' }}
                    </span>
                </div>
                
            </div>
            <div class="created">{{post.created_at}}</div>
        </div>
    </div>
</template>

<script>


  export default {
    name: 'Post',
    methods:{
        more(){
            console.log(this.post);
            document.getElementById('post'+this.post.id).style.width = "50%"
            document.getElementById('post'+this.post.id).style.position = "absolute"
            document.getElementById('post'+this.post.id).style.zIndex = "999"
            this.show_more = true
        },
        close(){
            document.getElementById('post'+this.post.id).style.width = "300px"
            document.getElementById('post'+this.post.id).style.position = "unset"
            document.getElementById('post'+this.post.id).style.zIndex = "1"
            this.show_more = false
        },
        comments(){
           
        }
    },
    props:{
        post:{}
    },
    data: ()=>({
      show_more: false,
      show_comments: false
    }),
    components: {},
  }
</script>

<style scoped>
.post{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  width: 300px;
  height: 400px;
  background-color: rgba(240, 248, 255, 0.425);
  backdrop-filter: blur(3px);
  padding: 10px;
  transition: .2s ease;
  border-radius: 8px;
  margin: 30px;
}
.post:hover{
  transition: .2s ease;
  background-color: rgba(240, 248, 255, 0.747);
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
  transform: scale(1.2);
}
.header{
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.header .user{
    display: flex;
    gap: 10px;
    align-items: center;
}
.header img{
    border-radius: 50%;
}
.header .close{
    cursor: pointer;
}
.header .username{
    font-size: 14px;
    font-weight: 500;
    color: rgb(57, 33, 58);
}
.header .star{
    font-size: 14px;
    display: flex;
    align-items: center;
}
.mdi-star::before {
    color: rgb(196, 166, 0);
}
.body{
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    gap: 20px;
    height: 250px;
}
.body .caption{
    max-height: 70px;
    overflow-y: scroll;
}
.body .caption::-webkit-scrollbar {
    display: none;
}
.body .photo{
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.caption span{
    font-size: 12px;
    opacity: .8;
    cursor: pointer;
}
.photo img{
    width: 280px;
    height: auto;
}
.footer .created{
    font-size: 12px;
}
.comments{
    font-size: 12px;
}
.comments .title{
    cursor: pointer;
}
</style>
