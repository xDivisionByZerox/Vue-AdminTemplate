<template>
    <!-- Widget: user widget style 1 -->
    <div class="card card-widget widget-user">
        <!-- Add the bg color to the header using any of the bg-* classes -->
        <div class="widget-user-header" :class="isBackgroundImage?'bg-black':theme"
             :style="isBackgroundImage?`background: url('${BackgroundImage}');
                                        background-position: center center;`:''">
            <h3 class="widget-user-username">{{ name }}</h3>
            <h5 class="widget-user-desc">{{ description }}</h5>
        </div>
        <div class="widget-user-image">
            <img class="img-circle elevation-2" :src="profileImage" alt="User Avatar">
        </div>
        <div class="card-footer">
            <div class="row">
                <div class="col-sm-4 border-right">
                    <div class="description-block">
                        <h5 class="description-header">{{ infoList[0].count }}</h5>
                        <span class="description-text">{{ infoList[0].text }}</span>
                    </div>
                    <!-- /.description-block -->
                </div>
                <!-- /.col -->
                <div class="col-sm-4 border-right">
                    <div class="description-block">
                        <h5 class="description-header">{{ infoList[1].count }}</h5>
                        <span class="description-text">{{ infoList[1].text }}</span>
                    </div>
                    <!-- /.description-block -->
                </div>
                <!-- /.col -->
                <div class="col-sm-4">
                    <div class="description-block">
                        <h5 class="description-header">{{ infoList[2].count }}</h5>
                        <span class="description-text">{{ infoList[2].text }}</span>
                    </div>
                    <!-- /.description-block -->
                </div>
                <!-- /.col -->
            </div>
            <!-- /.row -->
        </div>
    </div>
    <!-- /.widget-user -->
</template>

<script>
    export default {
        name: "SocialUser.v1",
        props: {
            theme: {
                type: String,
                default: 'bg-info-active'
            },
            isBackgroundImage: {
                type: Boolean,
                default: false
            },
            BackgroundImage: {
                type: String,
                default: ''
            },
            name: {
                type: String
            },
            description: {
                type: String
            },
            profileImage: {
                type: String
            },
            infoList: {
                type: Array
            }
        },
        created () {

        }
    }
</script>

