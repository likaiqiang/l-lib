<template>
    <div class="dib">
        <input
            type="checkbox"
            :id="id"
            :disabled="disabled"
            v-model="val"                                                                                                                    
        >
        <label
            :for="id"
            class="ui-checkbox"
        ></label>
    </div>
</template>

<script>
import { createId } from "@/utils/tools";
export default {
    name:'ui-checkbox',
    data(){
        return {
            id:createId()
        }
    },
    props:{
        value:{
            default:false
        },
        label:{
            default:''
        },
        disabled:{
            type:Boolean,
            default:false
        }
    },
    // watch:{
    //   value:function(newVal,oldVal){
    //     debugger
    //     if(newVal != oldVal && !this.disabled){
    //       this.val = newVal
    //       this.$emit('input',newVal)
    //       this.$emit('change',newVal)
    //     }
    //   }
    // }
    computed:{
      val:{
        get(){
          return this.value
        },
        set(val){
          this.$emit('input',val)
          this.$emit('change',val)
        }
      }
    }
}
</script>

<style>

</style>
