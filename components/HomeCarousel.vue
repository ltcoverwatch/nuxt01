<template>
<div class="block">
    <el-carousel height="600px" :interval="8000">
        <el-carousel-item v-for="item in 2" :key="item">
            <h3 class="small">{{ item }}</h3>
            <div class="carousel-content">
                <el-button>button</el-button>
            </div>

        </el-carousel-item>
    </el-carousel>
</div>
</template>

<script>
export default {};
</script>

<style>
.carousel-content {
    max-width: 1200px;
    margin: 0 auto;
}

.el-carousel__item h3 {
    color: #475669;
    font-size: 14px;
    opacity: 0.75;
    line-height: 150px;
    margin: 0;
}

.el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
    background-color: #d3dce6;
}
</style>
