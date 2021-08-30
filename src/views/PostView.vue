<template>
    <div class="main">
        <div class="post">
            <h5>Wrote at: {{post.created_at}}</h5>
            <img :src="post.image" alt="">
            <p>{{post.caption}}</p>
            <cite>
            <img :src="post.user.avatar" alt="">{{post.user.username}}</cite>
        </div>
        <div class="comments">
            <comments :comments="post.comments" :postId="post.id"></comments>
        </div>
    </div>
</template>

<script>
import Comments from '../components/home/Comments.vue'
export default {
    mounted(){
    },
    components:{
        Comments
    },
    props:{
        id: {}
    },
    data: ()=>
        ({
            post:{
                id: 1,
                image: require('../assets/post.jpg'),
                caption:'Genesis Global Trading—the New York-based crypto firm that bills itself as a prime brokerage—turned over more than $8 billion worth of derivatives last quarter. Joshua Lim is the man behind those billions as the firms Head of Derivatives. Lim joined The Scoop this week to unpack Genesis second quarter report, explaining how new preferences among investors and traders have shaped the make up of derivatives. He told The Blocks Frank Chaparro that the growth of crypto-native hedge funds have increased their need for derivatives, including options and futures, to hedge their positions. I think its mostly crypto negative hedge funds that we deal with that were more willing to engage with us on hedging strategies," he said. As bitcoin was approaching $55,000, he said many were.The live Bitcoin price today is $39,152.58 USD with a 24-hour trading volume of $24,653,578,833 USD. Bitcoin is up 1.74% in the last 24 hours. The current CoinMarketCap ranking is #1, with a live market cap of $735,131,428,330 USD. It has a circulating supply of 18,776,068 BTC coins and a max. supply of 21,000,000 BTC coins.',
                rate: 3.5,
                comments:[
                {
                    id: 1,
                    content: 'so good!!',
                    likes: 7,
                    liked: true,
                    created_at:'August 04, 2021 05:36',
                    user: {
                    id: 2,
                    username: 'jack.nickelson',
                    avatar: require('../assets/avatar.jpg')
                    },
                },
                {
                    id: 1,
                    content: 'good luck!!',
                    likes: 3,
                    liked: false,
                    created_at:'August 04, 2021 05:36',
                    user: {
                    id: 3,
                    username: 'leo.dicaprio',
                    avatar: require('../assets/avatar.jpg')
                    },
                },
                ],
                user: {
                id: 1,
                username: 'liam.nesson',
                avatar: require('../assets/avatar.jpg')
                },
                created_at:'August 04, 2021 05:36'
                }
          
    })
}
</script>

<style scoped>
.main{
    width: 100%;
    min-height: 90vh;
    height: fit-content;
    padding: 20px;
    display: flex;
    align-items: flex-start;
    justify-content: flex-start;
    margin: auto;
}
.post{
    width: 80%;
    padding: 20px;
    display: flex;
    flex-direction: column;
    gap: 20px;
}
.post img{
    width: 100%;
    height: 400px;
}
.post cite{
    display: flex;
    align-items: center;
    gap: 7px;
}
.post cite img{
    width: 34px;
    height: 34px;
    border-radius: 50%;
}
.post p{
    text-align: center;
    line-height: 22px;
    font-weight: 500;

}
.comments{
    width: 20%;
}
@media screen and (max-width: 768px) {
    .main{
        flex-direction: column;
    }
    .post{
        width: 100%;
    }
    .post img{
        height: 200px;
    }
    .comments{
        width: 100%;
    }
}
</style>