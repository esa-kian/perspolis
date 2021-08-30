<template>
  <div class="main">
    <post v-for="post in posts" :key="post.id" :post="post"></post>
  </div>
</template>

<script>
import Post from '../components/home/Post.vue'
  export default {
    name: 'Home',
      data: ()=>({
        posts:[
          {
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
          },
          {
            id: 2,
            image: require('../assets/post.jpg'),
            caption:'The live Bitcoin price today is $39,152.58 USD with a 24-hour trading volume of $24,653,578,833 USD. Bitcoin is up 1.74% in the last 24 hours. The current CoinMarketCap ranking is #1, with a live market cap of $735,131,428,330 USD. It has a circulating supply of 18,776,068 BTC coins and a max. supply of 21,000,000 BTC coins.',
            rate: 3.5,
            comments:[
              {
                id: 1,
                content: 'so good!!',
                likes: 7,
                liked: false,
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
          },
          {
            id: 3,
            image: require('../assets/post.jpg'),
            caption:'The live Bitcoin price today is $39,152.58 USD with a 24-hour trading volume of $24,653,578,833 USD. Bitcoin is up 1.74% in the last 24 hours. The current CoinMarketCap ranking is #1, with a live market cap of $735,131,428,330 USD. It has a circulating supply of 18,776,068 BTC coins and a max. supply of 21,000,000 BTC coins.',
            rate: 3.5,
            comments:[
              {
                id: 1,
                content: 'so good!!',
                likes: 7,
                liked: false,
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
          },
          {
            id: 4,
            image: require('../assets/post.jpg'),
            caption:'The live Bitcoin price today is $39,152.58 USD with a 24-hour trading volume of $24,653,578,833 USD. Bitcoin is up 1.74% in the last 24 hours. The current CoinMarketCap ranking is #1, with a live market cap of $735,131,428,330 USD. It has a circulating supply of 18,776,068 BTC coins and a max. supply of 21,000,000 BTC coins.',
            rate: 3.5,
            comments:[
              {
                id: 1,
                content: 'so good!!',
                likes: 7,
                liked: false,
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
          },
          {
            id: 5,
            image: require('../assets/post.jpg'),
            caption:'The live Bitcoin price today is $39,152.58 USD with a 24-hour trading volume of $24,653,578,833 USD. Bitcoin is up 1.74% in the last 24 hours. The current CoinMarketCap ranking is #1, with a live market cap of $735,131,428,330 USD. It has a circulating supply of 18,776,068 BTC coins and a max. supply of 21,000,000 BTC coins.',
            rate: 3.5,
            comments:[
              {
                id: 1,
                content: 'so good!!',
                likes: 7,
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
          },
          {
            id: 6,
            image: require('../assets/post.jpg'),
            caption:'The live Bitcoin price today is $39,152.58 USD with a 24-hour trading volume of $24,653,578,833 USD. Bitcoin is up 1.74% in the last 24 hours. The current CoinMarketCap ranking is #1, with a live market cap of $735,131,428,330 USD. It has a circulating supply of 18,776,068 BTC coins and a max. supply of 21,000,000 BTC coins.',
            rate: 3.5,
            comments:[
              {
                id: 1,
                content: 'so good!!',
                likes: 7,
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
          },
            {
            id: 7,
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
          },
          {
            id: 8,
            image: require('../assets/post.jpg'),
            caption:'The live Bitcoin price today is $39,152.58 USD with a 24-hour trading volume of $24,653,578,833 USD. Bitcoin is up 1.74% in the last 24 hours. The current CoinMarketCap ranking is #1, with a live market cap of $735,131,428,330 USD. It has a circulating supply of 18,776,068 BTC coins and a max. supply of 21,000,000 BTC coins.',
            rate: 3.5,
            comments:[
              {
                id: 1,
                content: 'so good!!',
                likes: 7,
                liked: false,
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
          },
          {
            id: 9,
            image: require('../assets/post.jpg'),
            caption:'The live Bitcoin price today is $39,152.58 USD with a 24-hour trading volume of $24,653,578,833 USD. Bitcoin is up 1.74% in the last 24 hours. The current CoinMarketCap ranking is #1, with a live market cap of $735,131,428,330 USD. It has a circulating supply of 18,776,068 BTC coins and a max. supply of 21,000,000 BTC coins.',
            rate: 3.5,
            comments:[
              {
                id: 1,
                content: 'so good!!',
                likes: 7,
                liked: false,
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
          },
          {
            id: 10,
            image: require('../assets/post.jpg'),
            caption:'The live Bitcoin price today is $39,152.58 USD with a 24-hour trading volume of $24,653,578,833 USD. Bitcoin is up 1.74% in the last 24 hours. The current CoinMarketCap ranking is #1, with a live market cap of $735,131,428,330 USD. It has a circulating supply of 18,776,068 BTC coins and a max. supply of 21,000,000 BTC coins.',
            rate: 3.5,
            comments:[
              {
                id: 1,
                content: 'so good!!',
                likes: 7,
                liked: false,
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
          },
          {
            id: 11,
            image: require('../assets/post.jpg'),
            caption:'The live Bitcoin price today is $39,152.58 USD with a 24-hour trading volume of $24,653,578,833 USD. Bitcoin is up 1.74% in the last 24 hours. The current CoinMarketCap ranking is #1, with a live market cap of $735,131,428,330 USD. It has a circulating supply of 18,776,068 BTC coins and a max. supply of 21,000,000 BTC coins.',
            rate: 3.5,
            comments:[
              {
                id: 1,
                content: 'so good!!',
                likes: 7,
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
          },
          {
            id: 12,
            image: require('../assets/post.jpg'),
            caption:'The live Bitcoin price today is $39,152.58 USD with a 24-hour trading volume of $24,653,578,833 USD. Bitcoin is up 1.74% in the last 24 hours. The current CoinMarketCap ranking is #1, with a live market cap of $735,131,428,330 USD. It has a circulating supply of 18,776,068 BTC coins and a max. supply of 21,000,000 BTC coins.',
            rate: 3.5,
            comments:[
              {
                id: 1,
                content: 'so good!!',
                likes: 7,
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
          },
        ]
    }),
    components: {
        Post
    },
  }
</script>

<style scoped>
.main{
    width: 100%;
    height: auto;
    padding: 40px 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    margin: auto;

}
</style>
