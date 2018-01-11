<template>
    <div class="e-cardShare">
        <div class="shareSection" @click="fbShare">
            <img src="../assets/fb.png" alt="點我Facebook分享" title="點我Facebook分享">
        </div>
        <div class="shareSection" v-if="!device" @click="msgShare">
            <img src="../assets/msg.png" alt="點我messenger分享" title="點我messenger分享">
        </div>
        <div class="shareSection" @click="lineShare">
            <img src="../assets/line.png" alt="點我line分享" title="點我line分享">
        </div>
        <div class="shareSection" @click="showFw"> 
            <img src="../assets/email.png" alt="點我Email分享" title="點我Email分享">
        </div>    
        <div class="emailForm" v-if='isFw'>
            <div class="supClose" @click="showFw"></div>
            <form id="fwEmail" :action="fwApi" method="post" @submit.prevent="handle_submit">
                <div class="closeIt" @click="showFw">
                    <span></span>
                    <span></span>
                </div>                
                <h2>轉寄功能</h2>
                <div class="sendTo">
                    <input type="text" v-model="sender" name="sender" placeholder="寄件者姓名"><p>寄給</p><input type="text" v-model="recive" name="recive" placeholder="收件者姓名">   
                </div>
                <label for="target">收件者Email:</label>
                <input type="email" v-model="address" name="target" required placeholder="xxx@gamil.com">
                <input type="submit" value="送出">
            </form>
        </div>                           
    </div>
</template>

<script>

import Utils from 'udn-newmedia-utils'

export default {
    props: ['href'],
    data: function() {
        return {
            isFw: false,
            // fwApi: 'http://localhost:2022/testemail/gmail.php',
            fwApi: null,
            device: null,
            address: null,
            sender: null,
            recive: null,
        }
    },
    methods: {
        lineShare: function() {
            ga("send", {
                "hitType": "event",
                "eventCategory": "Line Share",
                "eventAction": "click",
                "eventLabel": "[" + Utils.detectPlatform() + "] [" + document.querySelector('title').innerHTML + "] [line share]"
            });
            if(Utils.detectMob()){
                //手機
                window.location.href="//line.me/R/msg/text/?" + document.querySelector('title').innerHTML + "%0D%0A%0D%0A" + document.querySelector('meta[property="og:description"]').content + "%0D%0A%0D%0A" + window.location.href;
            } else {
                window.open("https://lineit.line.me/share/ui?url=" + window.location.href);
            }
        },
        fbShare: function() {
            const vm = this
            FB.ui({
                method: 'share',
                display: 'popup',
                mobile_iframe: true,
                href: vm.$props.href
            })
            ga("send", {
                "hitType": "event",
                "eventCategory": "facebook Share",
                "eventAction": "click",
                "eventLabel": "[" + Utils.detectPlatform() + "] [" + document.querySelector('title').innerHTML + "] [facebook share]"
            });                                     
        },
        msgShare: function() {
            const vm = this
            window.FB.ui({
              method: 'send',
              link: vm.$props.href,
            });
            ga("send", {
                "hitType": "event",
                "eventCategory": "messenger Share",
                "eventAction": "click",
                "eventLabel": "[" + Utils.detectPlatform() + "] [" + document.querySelector('title').innerHTML + "] [messenger share]"
            });                  
        },
        showFw: function() {
            this.isFw ?
                this.isFw = false :
                this.isFw = true
        },
        handle_submit: function() {
            alert('未開放');
        }
    },
    mounted() {
        this.device = Utils.detectMob()
    }
}
</script>

<style lang="scss" scoped>
    .e-cardShare{
        width: 100%;
        height: 60px;
        display: flex;
        align-items: center;
        justify-content: center;
        .shareSection{
            position: relative;
            height: 40px;
            width: 40px;
            cursor: pointer;
            margin: 0 15px;
            img{
                width: 100%;
                height: 100%;
            }
        }
    }
    .emailForm{
        position: fixed;
        z-index: 0;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        padding-top: 100px;
        background-color: rgba(black, .8);
        display: flex;
        flex-direction: column;
        align-items: center;
        cursor: pointer;
    }
    #fwEmail{
        position: relative;
        z-index: 20;
        width: 80%;
        max-width: 500px;
        padding: 20px 25px;
        background-color: #FFF;
        border-radius: 15px;
        cursor: auto;
        h2{
            margin: 0;
        }
        input[type="email"]{
            width: 100%;
            border: none;
            border-bottom: 1px solid black;
        }
        input[type="submit"]{
            display: block;
            margin: 20px 0 0 auto;
            width: 120px;
            height: 30px;
            text-align: center;
            border-radius: 15px;
        }
    }
    .sendTo{
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin-bottom: 10px;
        input[type="text"]{
            width: 33%;
            border: none;
            border-bottom: 1px solid black;   
            text-align: center;         
        }
        p{
            color: black;
            text-align: center;

        }        
    }
    .supClose{
        position: absolute;
        z-index: 5;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;

    }
    .closeIt{
        position: absolute;
        top: -30px;
        right: -30px;
        width: 30px;
        cursor: pointer;
        z-index: 9999;
        span{
            position: absolute;
            top: 14px;
            left: 2px;
            display: block;
            width: 26px;
            height: 2px;
            background-color: #fff;
            pointer-events: none;
            &:nth-child(1){
                transform: rotate(45deg);
            }
            &:nth-child(2){
                transform: rotate(-45deg);
            }
        }
    }
    @media screen and (min-width: 768px) and (max-width: 1024px) {
        .e-cardShare{
            .shareSection{
                height: 45px;
                width: 45px;
            }
        }
    }    
    @media screen and (min-width: 1024px){
        .e-cardShare{
            .shareSection{
                height: 50px;
                width: 50px;
            }
        }       
    }       
</style>
