<template>
    <div class="homepage-container">
        <div class="slider-container">
            <el-carousel height="auto">
                <el-carousel-item style="height:180px">
                    <div class="daily-word-container">
                        <div class="daily-word-container-inner">
                            <div>Emotional Damage</div>
                            <p>relating to the emotions</p>
                            <p>情绪上被无情打击</p>
                        </div>

                    </div>
                </el-carousel-item>
                <el-carousel-item>
                    <div class="daily-word-container">
                        <div class="daily-word-container-inner">
                            <div>FUIYOH</div>
                            <p>totally agree with sth.</p>
                            <p>很好的，很中意的，表示赞同</p>
                        </div>
                    </div>
                </el-carousel-item>
                <el-carousel-item>
                    <div class="daily-word-container">
                        <div class="daily-word-container-inner">
                            <div>HIYAA</div>
                            <p>feel regretful about sth. or sb.</p>
                            <p>表示遗憾的</p>
                        </div>
                    </div>
                </el-carousel-item>
            </el-carousel>
        </div>
        <div class="body-container">
            <div class="bottom-banner"><span>Stay Hungry, Stay Foolish！</span></div>
            <el-row justify="space-around">
                <el-col :span="11">
                    <el-card shadow="always" @click="redirect('group-manage')">词组管理</el-card>
                </el-col>
                <el-col :span="11">
                    <el-card shadow="always" @click="redirect('record')">单词查询</el-card>
                </el-col>
            </el-row>
            <el-row justify="space-around" style="margin-top: 15px;">
                <el-col :span="11">
                    <el-card shadow="always" @click="redirect('recite')"> 单词背诵 </el-card>
                </el-col>
                <el-col :span="11">
                    <el-card shadow="always" @click="redirect('square')">词组广场
                        </el-card>
                </el-col>
            </el-row>
            <el-row justify="space-around" style="margin-top: 15px;">
                <el-col :span="11">
                    <el-card shadow="always" @click="redirect('feedback')">反馈建议</el-card>
                </el-col>
                <el-col :span="11">
                    <el-card shadow="always" @click="redirect('settings')">用户设置</el-card>
                </el-col>
            </el-row>
        </div>
    </div>
</template>

<script setup lang="ts">
import { useRouter } from 'vue-router';

const router = useRouter()
function redirect(condition: string) {
    if (condition === 'recite') router.push('/recite/normal')
    if (condition === 'group-recite') router.push('/group-recite')
    if (condition === 'cycling') router.push('/cycling')
    if (condition === 'feedback') router.push('/feedback')
    if (condition === 'group-manage') router.push('/group-manage')
    if (condition === 'record') router.push('/record-word')
    if (condition === 'settings') router.push('/settings')
    if (condition === 'help') router.push('/help')
    if (condition === 'square') router.push('/square')
}
</script>

<style lang="less" scoped>
.homepage-container {
    .slider-container {
        height: 180px;
        background-color: grey;

        img {
            object-fit: fill;
        }

        .daily-word-container {
            padding: 3px 5px;
            // background-color: rgba(0, 255, 255, 0.6);
            background-color: rgb(255, 124, 10);

            height: 100%;
            display: flex;
            flex-direction: row;
            justify-content: space-around;
            align-items: center;

            &-inner {
                width: 80%;
                height: 50%;
                margin: 0 auto;
                text-align: center;

                &>div {
                    color: white;
                }

                &>p {
                    color: white;
                }
            }
        }


    }

    .body-container {
        margin-top: 15px;
    }

    .bottom-banner {
        margin: 10px auto;
        font-size: 12px;
        text-align: center;
        color: #ff7c0a;
        cursor: pointer;
    }
}
</style>