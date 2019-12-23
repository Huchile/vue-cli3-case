<template>
    <div class="main">
        <div class="left">
            <Left></Left>
        </div>
        <div class="right">
            <div class="top">
                <img src="img/banner.jpg" alt="banner">
            </div>
            <div class="bottom">
                <Right></Right>
            </div>
        </div>
    </div>
</template>
<script>
import Left from '../components/Left.vue'
import Right from '../components/Right.vue'
export default {
    components: {
        Left,
        Right
    }
}
</script>
<style>
* { padding: 0; margin: 0;}
.main {margin: 20px auto;width: 1200px; }
.left,.right {background-color: #f5f5f5;}
.left {width: 100px; float: left; margin-right: 10px;}
.right {width: 1000px;float: left;margin-left: 10px;}
.top img {height: 200px;width: 100%;}
</style>
