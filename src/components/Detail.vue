<template>

    <div class="detail">

        <div class="detail_img">
            <img :src="item['PHOTO'][0]" alt=""/>
        </div>

        <div class="detail_name">{{ item['NAME'] }}</div>

        <div class="detail_vendor-code">Артикул: {{ id }}</div>

        <div class="detail_price">{{ item['PRICE'] }}</div>

        <div class="detail_desc">{{ item['DESCRIPTION'] }}</div>

        <div class="detail_size">

            <span>Размер</span>

            <div class="detail_size-sizes">
                <span v-for="(size, id) in item['SIZE']" :key="`size_${id}`">
                    {{ size }}
                </span>
            </div>

        </div>

        <div class="detail_button">Добавить в корзину</div>

    </div>

</template>

<script>
    export default {
        name: "Detail",
        props: {
            id: String
        },
        data(){
            return {
                item: {}
            };
        },
        mounted(){

            fetch(
                'http://192.168.64.2/api/detail.php',
                {
                    method: 'POST',
                    headers: {
                        'Accept': 'application/json',
                        'Content-Type': 'application/json'
                    },
                    mode: 'cors',
                    body: JSON.stringify({id: this.id})
                }
            ).then(res => res.json()).then(res => {

                console.log(res);

                this.item = res;

            }).catch(err => {});
        }
    }
</script>

<style scoped>

    .detail{
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-top: 3rem;
    }

    .detail .detail_img{
        width: 70vw;
        height: auto;
        margin-bottom: 3rem;
    }

    .detail .detail_img img{
        width: 100%;
        height: 100%;
    }

    .detail .detail_name{
        font-size: 2.5rem;
    }

    .detail .detail_vendor-code{
        font-size: .7rem;
        color: grey;
    }

    .detail .detail_price{
        font-style: italic;
        margin-top: 1rem;
        margin-bottom: 1rem;
        color: grey;
    }

    .detail .detail_desc{
        font-size: .7rem;
        color: grey;
    }

    .detail .detail_size{
        margin-top: 2rem;
        color: grey;
        font-size: .9rem;
        display: flex;
        flex-direction: column;
    }

    .detail .detail_size > span{
        text-align: center;
    }

    .detail .detail_size .detail_size-sizes{
        margin-top: .8rem;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .detail .detail_size .detail_size-sizes span{
        border: 1px solid grey;
        margin-left: .8rem;
        padding: 3px;
        width: 20px;
        display: flex;
        height: 20px;
        align-items: center;
        justify-content: center;
    }

    .detail .detail_button{
        margin-top: 3rem;
        border: 1px solid orange;
        padding: 1rem 1.5rem;
        background-color: orange;
        color: white;
        font-size: .8rem;
        text-transform: uppercase;
    }

</style>