<template>
    <div>



        <section id="topbar">
            <div class="title">
              <a href="javascript:void(0)" @click="$router.go(-1)" ><i class="fa fa-angle-left"></i></a>
                <p>{{ $t('Information.value') }}</p>
                <LanguageComponent/>
            </div>
        </section>

        <section id="listmenus" class="info">
            <div class="container-fluid">
                <ul style="list-style:none" class="p-0">
                    <!-- <li><img src="img/users.png" class="icon"> Avatar <img src="img/11.png" class="userimg"></li> -->
                    <!-- <li><a href="javascript:void(0)"><img src="img/ph.png" class="icon"> Mobile Number <span>{{ row.user.mobile }}</span> </a></li> -->
                    <li style="padding: 7px 5px;background: #5aff00;margin: 1px;"><router-link class="text-dark" :to="{name:'bankAccount'}"> {{ $t('Bank_Card.value') }} <span>  </span></router-link> </li>
                    <li style="padding: 7px 5px;background: #5aff00;margin: 1px;"><router-link class="text-dark" :to="{name:'RechangePass'}"> {{ $t('Password_Management.value') }} </router-link>
                    </li>

                </ul>
            </div>
        </section>


    </div>
</template>
<script>
export default {
    data(){
        return {
            row:{
                user:{},
            },
        }
    },
    methods: {
         async getData(){
            var id = localStorage.getItem('userid');
            var res = await this.callApi('get',`/api/front/teamdetails?id=${id}`,[]);
            this.row = res.data;
        },
    },
    mounted() {
            this.getData();

    },
}
</script>
