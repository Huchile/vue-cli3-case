<template>
    <div name="show">
        <ul class="goodList">
            <li v-for="good in list">
                <img v-bind:src="good.img">
                <p>{{good.goodName}}</p>
            </li>
        </ul>
    </div>
</template>
<script>
    export default {
        name: "show",
        data(){
            var _this=this;
            var url="";
            if(_this.goodId==1){
                url="json/computer.json";
            }else if(_this.goodId==2){
                url="json/phone.json";
            }else{
                url="json/computer.json";
            }
            this.$http.get(url).then(function(res){
                 _this.list=res.data;
            })
            return{
                list:[]
            }
        },
        props:{
            goodId:Number  // 父子组件传值
        },
        watch:{
            goodId(){
                var _this = this;
                var url = "";
                if(_this.goodId == 1){
                    url = "json/computer.json";
                }else if (_this.goodId == 2){
                    url = "json/phone.json";
                }else{
                    url="json/computer.json";
                }
                this.$http.get(url).then(function(res){
                     _this.list=res.data;
                })
                return{
                    list:[]
                }
            }
        }
    }
</script>
<style type="text/css">
    .goodList {margin-top: 10px;}
    .goodList li{ width: 200px; height: 200px; list-style-type: none; float: left; font-size:9px; color: red; margin-bottom: 30px; }
    .goodList img{ width: 180px; height: 180px; }
    .goodList p{ width: 100%; box-sizing: border-box;padding: 0 10px;overflow: hidden; display: -webkit-box; -webkit-box-orient: vertical; -webkit-line-clamp: 2; word-break: break-all; }
</style>
