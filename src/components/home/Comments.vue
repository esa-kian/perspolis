<template>

      <div class="content">
         
            
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
</template>

<script>
export default {
    name: 'Comments',
    components:{
    },
    methods:{ 
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
    },
    data: () => ({
        comment: '',
  }),
};
</script>
<style scoped>


.content{
    width: 100%;
    height: auto;
    max-height: 100vh;
    padding: 10px;
    overflow-y: scroll;
}
.content::-webkit-scrollbar {
    display: none;
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
    border-radius: 8px;
    padding: 7px;
    outline: none;
    background-color: rgba(16, 0, 104, 0.137);
    transition: .2s ease;
}
textarea.context:focus{
    background-color: rgba(16, 0, 104, 0.041);
    transition: .2s ease;
}
.post-comment
button{
    width: 18%;
    background-color: rgba(16, 0, 104, 0.137);
    border-radius: 8px;

}
</style>
