<template>
    <el-submenu :index="parent.name">
        <template slot="title">
            <i :class="parent.icon"></i>
            <span slot="title">{{parent.title}}</span>
        </template>
        <template v-for="(item,index) in parent.list">
            <WsubMenu :key="index" v-if="item.list.length>0" :parent="item"/>
            <el-menu-item :index="item.name" v-else :key="index">
                <i :class="item.icon"></i>
                <span slot="title">{{item.title}}</span>
            </el-menu-item>
        </template>
    </el-submenu>
</template>
<script>
export default {
    name:'WsubMenu',
    props:{
        parent:Object
    }
}
</script>
