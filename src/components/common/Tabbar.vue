<template>
    <div class="tabbar">
        <ul>
            <li v-for="(item,index) in routerList" :key="index" @click="switchTab(item.path)">
                <img :src="$route.path.includes(item.path) ? item.selected : item.active" alt="">
                <span>{{item.title}}</span>
            </li>
        </ul>

    </div>
    
</template>
<script>
    export default {
        data(){
            return{
                routerList:[
                    {
                        title:"首页",
                        path:"/home",
                        active:"./images/homeicon.png",
                        selected:"./images/home-select.png",
                    },
                    {
                        title:"分类",
                        path:"/list",
                        active:"./images/homeicon.png",
                        selected:"./images/home-select.png",
                    },
                    {
                        title:"购物车",
                        path:"/cart",
                        active:"./images/homeicon.png",
                        selected:"./images/home-select.png",
                    },
                    {
                        title:"我的",
                        path:"/my",
                        active:"./images/homeicon.png",
                        selected:"./images/home-select.png",
                    },
                ]
            }

        },
        methods:{
            switchTab(path){
                if( this.$route.path == path) return;
                this.$route.path.replace(path);

            }
        }

    }

</script>

<style scoped>
.tabbar{
    position: fixed;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 60px;
    background-color: white;
    z-index: 999;
}
.tabbar ul{
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 100%;
    height: 100%;

}
.tabbar ul li{
    display: flex;
    flex-direction: column;
    align-items: center;
}
.tabbar ul li img{
    width: 0.826666rem;
    height: 0.826666rem;
}
.tabbar ul li span{
    font-size: 16px;
}
</style>