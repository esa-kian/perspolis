<template>
    <div class="main">
        <div class="form">
            <h1>Create new post</h1>
            <div class="photo">
                <label for="photo">Photo</label>
                <input type="file" name="photo" id="photo">
            </div>
            <div class="body">
                <label for="body">Caption</label>
                <textarea v-model="body" name="body" id="body" cols="30" rows="10"></textarea>
            </div>
            <button @click="submit">Submit</button>
        </div>
    </div>
</template>

<script>
export default {
    methods:{
        submit(){
          

            let posts = [];

            if(localStorage.posts){
                posts = JSON.parse(localStorage.posts)
            } 

            let post  = {
                id: posts.length + 1,
                image: require('../assets/post.jpg'),
                caption: this.body,
                rate: 0,
                comments:[
                
                ],
                user: {
                    id: 1,
                    username: 'Pink.floyd',
                    avatar: require('../assets/avatar.jpg')
                },
                created_at: Date()
            }

            posts.push(post);

            localStorage.posts = JSON.stringify(posts);

            this.$router.push('/profile');
        }
    },
    data: ()=>
        ({
            body: ""
    })
}
</script>

<style scoped>
.main{
    width: 100%;
    height: 90vh;
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    margin: auto;
}
.form{
    background-color: rgba(240, 248, 255, 0.637);
    padding: 20px;
    border-radius: 8px;
    display: flex;
    flex-direction: column;
}
.body, .photo{
    display: flex;
    flex-direction: column;
    gap: 20px;
}
</style>