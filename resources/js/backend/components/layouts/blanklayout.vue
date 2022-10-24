<template>
    <div>
        <h1 v-if="Frontloader">loading....</h1>

    <!-- <section id="call">
      <img :src="$asseturl+'frontend/img/phone.png'" alt="phone" />
    </section> -->

        <slot></slot>

<section style="padding: 40px;"></section>
        <section id="menus">
            <div class="container-fluid">
                <div class="row">
                    <div class="col-3 p-0" style="width: 20% !important;">
                        <div class="menu">
                            <router-link :to="{name:'Authuser'}">
                                <i class="fas fa-house-user" style="font-size: 30px;    color: green;"></i>
                                <p>Home</p>
                            </router-link>
                        </div>
                    </div>
                    <div class="col-3 p-0" style="width: 20% !important;">
                        <div class="menu">
                            <router-link :to="{name:'UserTeam'}">
                                <i class="fas fa-users fa-fw" style="font-size: 30px;color: green;"></i>
                                <p>Team</p>
                            </router-link>
                        </div>
                    </div>
                    <div class="col-3 p-0" style="width: 20% !important;">
                        <div class="menu" style="position: relative;">
                            <router-link :to="{name:'Usertask'}" style="position: absolute;bottom: -37px;left: 13%;background: white;padding: 6px;border-top-left-radius: 30px;border-top-right-radius: 30px;">
                                <i class="fab fa-youtube fa-fw" style="font-size: 40px;    color: red;"></i>
                                <p>Video</p>
                            </router-link>
                        </div>
                    </div>
                    <div class="col-3 p-0" style="width: 20% !important;">
                        <div class="menu">
                            <a :href="$asseturl+'NEPA_Q_MART_16182413.apk'">
                                <i class="fas fa-mobile-alt fa-fw" style="font-size: 30px;color: green;"></i>
                                <p>App</p>
                            </a>
                        </div>
                    </div>
                    <div class="col-3 p-0" style="width: 20% !important;">
                        <div class="menu">
                            <router-link :to="{name:'Useraccount'}">

                                <i class="fas fa-user-circle fa-fw" style="font-size: 30px;    color: green;"></i>
                                <p>Account</p>
                            </router-link>
                        </div>
                    </div>


                </div>
            </div>
        </section>

    </div>
</template>
<script>
  export default {
    created() {
                this.createlink('frontend/css/bootstrap.min.css');
        this.createlink('frontend/css/style.css');
        this.createlink('frontend/css/font-awesome.min.css');

        this.createscript('frontend/js/bootstrap.bundle.min.js');
        this.createscript('frontend/js/bootstrap.min.js');
    },
    data(){
        return {

        }},
    watch: {
        '$route': {
            handler(newValue, oldValue) {
                window.scrollTo(0,0);
            },
            deep: true
        }
    },
    mounted() {


    },
    methods: {
        createlink(url=''){
            let recaptchaScript = document.createElement('link')
            recaptchaScript.setAttribute('href', this.$asseturl+url)
            recaptchaScript.setAttribute('rel', 'stylesheet')
            document.head.appendChild(recaptchaScript)
        },
        createscript(url=''){
            let recaptchaScript = document.createElement('script')
            recaptchaScript.setAttribute('src', this.$asseturl+url)
            document.body.appendChild(recaptchaScript)
        }
    }
  }
</script>
<style>
.col-6.amount_item span {
  border: 2px solid #e8ba31;
  display: block;
  text-align: center;
  margin: 6px 0px;
  padding: 4px 3px;
  cursor: pointer;
}
</style>
