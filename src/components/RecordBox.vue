<template>
    <div class="box">
        <div class="img-box">
            <img :src="disk.poster" />
        </div>
        <h1>{{disk.title.toUpperCase()}}</h1>
        <div class="song-info">
            <p class="song-author">{{disk.author}}</p>
            <p>{{disk.year}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        disk: Object
    }
}
</script>

<style lang="scss" scoped>
    .box {
        width: 200px;
        height: 350px;
        background-color: #2e3a46;
        margin: 10px 20px;

            .img-box {
                width: 150px;
                height: 150px;
                margin-top: 20px;

                img {
                    width: 100%;
                    height: 100%;
                }

            }

            h1 {
                color: #fff;
                font-family: Arial, Helvetica, sans-serif;
                font-size: 23px;
                text-align: center;
                padding: 20px 12px;

            }

            .song-info {
                text-align: center;
                font-family: Arial, Helvetica, sans-serif;
                color: #62666b;
                font-weight: bold;

                .song-author {
                    font-size: 19px;

                }

            }
        }
</style>