<template>
    <div class="card" v-if="ind % 2 === 0">
        <img :src="require(`./img/${content.contentImg}.svg`)" alt="">
        <div class="card-content">
            <h1>{{content.contentHead}}</h1>
            <p>{{content.contentPara}}</p>
        </div>
    </div>
    <div class="card even" v-else>
        <div class="card-content">
            <h1>{{content.contentHead}}</h1>
            <p>{{content.contentPara}}</p>
        </div>
        <img :src="require(`./img/${content.contentImg}.svg`)" alt="">
    </div>
</template>
<script>
export default {
    name: 'Cards',
    props: [
        'content',
        'ind'
    ],
    setup(props){
        let ord = props.ind % 2 === 0 ? 'column' : 'column-reverse';
        return { ord };
    }
}
</script>
<style>
    .card{
        padding: 50px;
        display: flex;
        justify-content: space-around;
        align-items: center;
        gap: 10px;  
    }
    .card img{
        width: 100%;
    }
    .card.even{
        background: #f6f6f6;
    }
    .card .card-content{
        padding: 40px;
    }
    .card .card-content h1{
        font-size: 2rem;
    }
    .card .card-content p{
        font-size: 1.3rem;
        line-height: 1.5;
        color: #23272a;
        margin-top: 20px;
    }
    @media(max-width: 1000px){
        .card .card-content h1{
        font-size: 1.6rem;
        }
        .card .card-content p{
            font-size: 1rem;
            line-height: 1.5;
            color: #23272a;
            margin-top: 20px;
        }
    }
    @media(max-width: 770px){
        .card{
            flex-direction: v-bind(ord);
        }
        .card .card-content h1{
        font-size: 1.3rem;
    }
        .card .card-content p{
            font-size: 0.8rem;
            line-height: 1.5;
            color: #23272a;
            margin-top: 20px;
        }
    }
</style>