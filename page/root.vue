<style lang="less">
    @import "style";
    nav{
        a{
            color:green;
        }
    }
</style>
<template>
    <header><h1>{{title}}</h1></header>
    <nav>
        <a v-link="{name:'home'}">page1</a>
        <a v-link="{path:'/inner?a=1'}">page2</a>
        <a v-link="{path:'/inner/123'}">page3</a>
    </nav>
    <p>路径：{{$route.path}}</p>
    <p>匹配：{{$route.params | json}}</p>
    <p>参数：{{$route.query | json}}</p>
    <router-view></router-view>
</template>
<script>
    module.exports = {
        data:function(){
            return {
                title:"Main Title12"
            }
        },
        replace:false,
        ready:function(){
            this.$on('alert',function(a){
                alert(a);
            });
        }
    }
</script>