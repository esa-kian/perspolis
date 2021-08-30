<template>
    <div class="main">
        <div class="profile">
            <div :style="{ 'background-image': 'url('+ cover +')'}" class="header">
                <div class="user">
                    <div class="avatar">
                        <img :src="avatar" :alt="username">
                        <label for="avatar"></label>
                        <input :disabled="!editable" type="file" hidden name="avatar" id="avatar">
                    </div>
                    <div class="name"> 
                        <input :disabled="!editable" :class="[!editable?'deactive':'active']" type="text" v-model="username" name="" id=""> 
                    </div>
                </div>
                <div class="follows">
                        
                    <div class="followers">{{'Followers: '+(followers > 999999 ? Math.round(followers/1000000, 1) + ' M': ( followers > 999 ? Math.round(followers/1000, 2) + ' K':followers))}}</div>
                    <div class="followings">{{'Followings: '+ followings }}</div>
                </div>
            </div>

            <div class="body">
                <div class="actions">
                    <router-link :to="'/create-post'">
                        <button> 
                            <v-icon>
                                mdi-plus
                            </v-icon>
                            New post
                        </button>
                    </router-link>
                    <button @click="editActive">
                        <v-icon>
                            mdi-pencil
                        </v-icon>
                        Edit</button>
                    <button>
                         <v-icon>
                            mdi-message
                        </v-icon>
                        Messages
                    </button>
                    <button>
                        <v-icon>
                            mdi-flag
                        </v-icon>
                        Saved posts
                    </button>
                    <button>
                       <v-icon>
                            mdi-wrench
                        </v-icon>
                        Settings
                    </button>
                    <button @click.prevent="signout">
                       <img src="../assets/exit.svg" width="28" height="28" alt="">
                          Signout
                    </button>
                </div>
                <div class="info">
                    <div class="fullname">
                        <div class="title">
                            Full name:</div>
                        <div class="value">
                            <input :disabled="!editable" :class="[!editable?'deactive':'active']" type="text" v-model="full_name" name="" id="">                            
                        </div>
                    </div>
                    <div class="email">
                        <div class="title">
                            Email:
                        </div>
                        <div class="value">
                            <input :disabled="!editable" :class="[!editable?'deactive':'active']" type="text" v-model="email" name="" id="">
                        </div>
                    </div>
                    <div class="bio">
                        <div class="title">
                            Bio:
                        </div>
                        <div class="value">
                            <textarea :disabled="!editable" :class="[!editable?'deactive':'active']" name="" v-model="bio" id="" cols="30" rows="10"></textarea>
                        </div>
                    </div>
                </div>
                <div class="posts">
                    <div v-for="post in posts.reverse()" :key="post.id">
                       <img :src="post.image" width="200" height="100" alt="">
                       <div class="caption">{{post.caption}}</div>
                       <div class="date">{{post.created_at}}</div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>

export default {
   
    mounted(){
        this.posts = JSON.parse(localStorage.posts);
    },
    methods:{
        editActive(){
            this.editable = !this.editable
        },
        signout(){
            localStorage.removeItem('authenticated')
            this.$router.push('/login')
            this.$router.go()
      }
    },
    data: ()=>({
        username: 'Pink.floyd',
        full_name:'Roger waters',
        email: 'roger.w@gmail.com',
        bio:'Pink Floyd were an English rock band formed in London in 1965',
        avatar: require('../assets/avatar.jpg'),
        cover: require('../assets/cover.jpg'),
        followers: 37449574,
        followings: 95,
        editable: false,
        posts: []
    })
}
</script>

<style scoped>
.main{
    width: 100%;
    height: auto;
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    margin: auto;
}
.profile{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    height: auto;
    background-color: rgba(240, 248, 255, 0.425);
    backdrop-filter: blur(3px);
    padding: 20px 0px;
    transition: .2s ease;
    border-radius: 8px;
}
.header{
    display: flex;
    width: 100%;
    height: 250px;
    max-height: 250px;
    justify-content: space-between;
    align-items: center;
    background-position: center;
    background-blend-mode: screen;
    background-color: rgba(213, 179, 214, 0.671);
    padding: 10px;
    background-size: 100%;
    background-attachment: fixed;

}
.header .user{
    display: flex;
    align-items: center;
    width: 30%;
    justify-content: flex-start;
    gap: 20px;
    position: relative;
}
.header .name,
.follows{
    font-size: 18px;
    font-weight: 600;
    text-shadow: 2px 2px 5px #edebf1;
    color: rgb(57, 33, 58);
}
.follows{
    background-color: rgba(43, 25, 44, 0.247);
    border-radius: 5px;
    padding: 10px;
    margin: 0 30px;
}

.header .name input{
    margin: 5px;
    padding: 10px;
    background-color: rgba(177, 134, 177, 0.555);
    text-shadow: 2px 2px 5px #edebf1;
    border-radius: 5px;
    min-width: 120px;
    width: 120px;
}
.header .name{
    background-color: rgba(43, 25, 44, 0.247);
    border-radius: 5px;
    padding: 10px;
    margin: 0 30px;
}
.follows div{
    margin: 5px;
    padding: 10px;
    background-color: rgba(177, 134, 177, 0.555);
    border-radius: 5px;
    transition: .3s ease;
    cursor: pointer;
}
.follows div:hover{
    transition: .3s ease;
    background-color: rgba(177, 134, 177, 0.89);
}
.header .avatar img{
    width: 128px;
    height: 128px;
    border-radius: 50%;
}
.avatar label{
    background-image: url('../assets/camera.svg');
    width: 44px;
    height: 44px;
    position: absolute;
    z-index: 990;
    background-position: center;
    background-size: 30px;
    background-color: #dba9fda8;
    border-radius: 50%;
    cursor: pointer;
    bottom: 0px;
    left: 80px;
} 
.body{
    display: flex;
    width: 100%;
    justify-content: flex-start;
    gap: 50px;
    padding: 20px;
}
.body .actions{
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: flex-start;
    gap: 10px;
}
.actions button{
    border-radius: 5px;
    transition: .3s ease;
    border: 1px solid rgba(82, 60, 60, 0.836);
    padding: 10px;
    width: 196px;
    height: 40px;
    display: flex;
    align-items: center;
}
.actions button:hover{
    transition: .3s ease;
    background-color: rgba(82, 60, 60, 0.178);
}
.fullname, .email, .bio{
    margin-bottom: 30px;
}
.active{
    border: 1px solid rgb(93, 67, 97);
    border-radius: 5px;
    padding: 10px;
    width: 160px;
    height: 45px;
    outline: none;
    transition: .3s ease;
}

input:disabled{
    padding: 10px;
    border: 1px solid transparent;
    color: rgb(43, 25, 44);
    border-radius: 5px;
    width: 160px;
    height: 45px;
    transition: .3s ease;
}
.bio textarea{
    resize: none;
    width: 360px;
    padding: 10px;
    height: 100px;
    overflow-y: scroll;
    scrollbar-width: none;
}
.bio textarea:disabled{
    width: 360px;
    padding: 10px;
    height: 100px;
}
.bio textarea::-webkit-scrollbar {
    display: none;
}
.body .title{
    font-size: 18px;
    font-weight: 500;
    color: rgba(82, 60, 60, 0.836);
    margin: 10px 0;
}
a {
    text-decoration: none;
    color: rgb(43, 25, 44);
}
.posts{
    display: flex;
    flex-direction: column;
}
</style>