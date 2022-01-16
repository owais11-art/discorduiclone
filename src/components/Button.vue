<template>
    <button class="btn" :class="{navbtn: !size}">
        <i class="bi bi-download" v-if="download" :style="{marginRight: margin}"></i>{{text}}
    </button>
</template>
<script>
export default {
    name: 'Button',
    props: [
        'text',
        'bgColor',
        'color',
        'size',
        'download',
        'margin'
    ],
    setup(props) {
        let styles = {
            bgColor: props.bgColor,
            color: props.color,
            size: props.size || '16px'
        };
        return {styles};
    },
}
</script>
<style>
    .btn{
        border: none;
        border-radius: 50px;
        padding: 10px 20px;
        background: v-bind('styles.bgColor');
        color: v-bind('styles.color');
        font-size: v-bind('styles.size');
        letter-spacing: 1px;
        cursor: pointer;
    }
    .btn:hover{
        color: #404eed;
        box-shadow: 0 10px 10px #1729f0;
    }
    @media(max-width: 750px){
        .navbtn{
            font-size: 0.7rem;
            padding: 10px 10px;
        } 
    }
</style>