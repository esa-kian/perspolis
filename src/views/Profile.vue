<template>
    <div class="main">
        <div class="profile">
            <div :style="{ 'background-image': 'url('+ cover +')'}" class="header">
                <div class="user">
                    <div class="avatar">
                        <img :src="avatar" :alt="username">
                    </div>
                    <div class="name">  
                        {{ username }}
                    </div>
                </div>
                <div class="follows">
                        
                    <div class="followers">{{'Followers: '+(followers > 999999 ? Math.round(followers/1000000, 1) + ' M': ( followers > 999 ? Math.round(followers/1000, 2) + ' K':followers))}}</div>
                    <div class="followings">{{'Followings: '+ followings }}</div>
                </div>
            </div>

            <div class="body">
                <div class="actions">
                    <button> 
                        <v-icon>
                            mdi-plus
                        </v-icon>
                        New post
                    </button>
                    <button>
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
                </div>
                <div class="info">
                    <div class="fullname">
                        <div class="title">Full name:</div>
                        <div class="value">
                            {{full_name}}
                        </div>
                    </div>
                    <div class="email">
                        <div class="title">
                            Email:
                        </div>
                        <div class="value">
                            {{email}}
                        </div>
                    </div>
                    <div class="bio">
                        <div class="title">
                            Bio:
                        </div>
                        <div class="value">
                            {{bio}}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    // pull request
    data: ()=>({
        username: 'Pink.floyd',
        full_name:'Roger waters',
        email: 'roger.w@gmail.com',
        bio:'Pink Floyd were an English rock band formed in London in 1965',
        avatar: require('../assets/avatar.jpg'),
        cover: require('../assets/cover.jpg'),
        followers: 37449574,
        followings: 95
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
    background-size: cover;
    background-attachment: fixed;

}
.header .user{
    display: flex;
    align-items: center;
    width: 30%;
    justify-content: flex-start;
    gap: 20px;
}
.header .name,
.follows{
    font-size: 18px;
    font-weight: 600;
    color: rgba(82, 60, 60, 0.836);
}

.header .avatar img{
    width: 128px;
    height: 128px;
    border-radius: 50%;
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
.body .title{
    font-size: 18px;
    font-weight: 500;
    color: rgba(82, 60, 60, 0.836);
    margin: 10px 0;
}
</style>