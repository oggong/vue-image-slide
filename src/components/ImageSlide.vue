<template>
    <div class="box" style="width:1100px; height: 600px; box-shadow: 0 0 25px -3px rgba(0,0,0, 0.4);">
        <img class="w-100 h-100" :src="image"/>
    </div>
</template>
<script>
    export default {
        name: 'image-slide',
        data() {
            return {
                // 사진 이미지 소스 경로
                images: ['images/img1.jpg', 'images/img2.jpg'],

                // 사진 이미지
                image: '',

                // 이미지 인덱스
                i: 0
            }
        },
        mounted() {
            this.slideShow();
        },
        methods: {
            slideShow() {
                this.image = this.images[this.i];

                if (this.i < this.images.length - 1) {
                    this.i++;
                }
                else {
                    this.i = 0;
                }
                setTimeout(() => {
                    this.slideShow();
                }, 3000)

            }
        }
    }
</script>
