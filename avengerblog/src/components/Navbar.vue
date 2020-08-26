

<template>
    <div class="header">
        <div class="nav">
            <h2>ＡＶＥＮＧＥＲ</h2>
            <ul class="navmenu">
                <li><router-link to="">Personal resume</router-link></li>
                <li><router-link to="">Project introduction</router-link></li>                
            </ul>
        </div>
        <div class="navline"></div>
    </div>
</template>

<script>
export default {
    name: 'navbar'
}
</script>

<style lang="scss">
.header {
    background: black;
}
.nav {
    padding: 25px 5vw;
    h2 {
        float: left;
        font-size: 35px;
        background: linear-gradient(to right, gray, lightgray, #fff);
        background-clip: text;
        color: transparent;
        margin-bottom: 20px;
    }
    ul {
        list-style: none;
        float: right;
        font-size: 20px;
        font-weight: bold;
        li {
            padding-top: 20px;
            padding-left: 15px;
            float: left;
            a{
                text-decoration: none;
                color: #fff;
            }
        }
        
    }
}

.navline {
    clear:both;
    height: 1px;
    background: rgb(246, 246, 246);
}
</style>


