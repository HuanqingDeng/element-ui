<template>
    <button class="el-button" :disabled="buttonDisabled" :type="nativeType" @click="handleClick"
    :class="[type?'el-button--'+type:'',{'is-disabled':buttonDisabled,'is-loading':loading}]">
        <i :class="isloading"></i>
        <i :class="icon" v-if="icon&&!loading"></i>
        <slot></slot>
    </button>
</template>
<script>
export default {
    name:'el-button',
    props:{
        disabled:Boolean,
        type:{
            type:String,
            default:'default'
        },
        loading:Boolean,
        isloading:String,
        icon:{
            type:String,
            defalut:''
        },
        nativeType:{
            type:String,
            defalut:'button'
        }
    },
    computed:{
        buttonDisabled(){
            return this.disabled;
        }
    },
    methods:{
        handleClick(evt){
            // console.log(evt);
            this.$emit('click',evt);//clickqqq父组件自定义的事件名
            //监听当前实例上的自定义事件。事件可以由vm.$emit触发。回调函数会接收所有传入事件触发函数的额外参数。
            //vm.$emit( event, […args] )
        }
    }
}
</script>
<style >

</style>
