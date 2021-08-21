<template>
  <div class="modal" :id="'modal'+postId">
      <div class="content">
          <span @click="closeComments" class="close">
                <v-icon>mdi-close</v-icon>
          </span>
            
            <div class="comment" v-for="comment in comments" :key="comment.id">
                <div class="user">
                    <div class="avatar">
                        <img :src="comment.user.avatar" alt="">
                    </div>
                    <div class="username">{{comment.user.username}}</div>
                </div>
                <div class="context">
                    {{comment.content}}
                </div>
                <div class="statics">
                    <div class="like">
                        {{comment.likes}}
                        <div @click="likeUnlike(comment)" :class="comment.liked?'liked':'unliked'"></div>
                    </div>
                    <div class="date">
                        {{comment.created_at}}
                    </div>
                </div>
            </div>
            <div class="post-comment">
                <textarea v-model="comment" name="" id="" class="context"></textarea>
                <button @click="submitComment">Send</button>
            </div>
      </div>
  </div>
</template>

<script>
export default {
    name: 'Comments',
    components:{
    },
    methods:{
        closeComments(){
            document.getElementById('modal'+this.postId).style.height = '0px';
        },
        submitComment(){
            let mycomment = {
                id: this.comments.length + 1,
                content: this.comment,
                likes: 0,
                liked: false,
                created_at: Date(),
                user: {
                  id: 1,
                  username: 'Pink.floyd',
                  avatar: require('../../assets/avatar.jpg')
                },
              };

              this.comments.push(mycomment);
        },
        likeUnlike(comment){
            if(comment.liked){
                comment.likes -= 1;
            }else{
                comment.likes += 1;
            }
            comment.liked = !comment.liked;
        }
    },

    props:{
        comments: [],
        postId: null
    },
    data: () => ({
        comment: '',
  }),
};
</script>
<style scoped>
.modal{
    display: flex;
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 0px;
    border-radius: 10px 10px 0 0;
    backdrop-filter: blur(3px);
    background-color: rgba(240, 248, 255, 0.747);
    transition: .3s ease;
    overflow:hidden;
}

.content{
    width: 100%;
    height: 400px;
    overflow-y: scroll;
    padding: 10px;
}
.content::-webkit-scrollbar {
    display: none;
}

span.close{
    cursor: pointer;
    position: absolute;
    z-index: 999;
    right: 10px;
}
.comment{
    display: flex;
    width: 100%;
    flex-direction: column;
    justify-content: flex-start;
    gap: 10px;
    margin: 20px 0;
    background-color: rgba(222, 212, 245, 0.575);
    border-radius: 10px;
    padding: 10px;
}
.user{
    display: flex;
    width: 100%;
    justify-content: flex-start;
    gap: 10px;
    align-items: center;
}
.user img{
    width: 44px;
    height: 44px;
    border-radius: 50%;
}
.statics{
    width: 100%;
    display: flex;
    justify-content: space-between;
}
.statics .date{
    font-size: 12px;
}
.like{
    display: flex;
}
.liked, .unliked{
    cursor: pointer;
    background-position: center;
    background-size: 20px;
    width: 25px;
    height: 25px;
    transition: .3s ease;
}
.liked{
    background-image: url('../../assets/heart_fill.svg');
}
.unliked{
    background-image: url('../../assets/heart.svg');
}
.post-comment{
    width: 100%;
    display: flex;
    justify-content: space-between;
}
textarea.context{
    width: 80%;
    resize: none;
    height: 60px;
}
.post-comment
button{
    width: 18%;
}
</style>
