<script>
import AppHeader from '@/components/AppHeader.vue'
import CompA from '@/components/CompA.vue'
import CompB from '@/components/CompB.vue'
import CompC from '@/components/CompC.vue'
import CompD from '@/components/CompD.vue'

export default {
  components: {AppHeader, CompA, CompB, CompC, CompD },
  data() {
    return {
      title:"Please choose your mood",
      activeComponent: '',
      values:[
        {
        id:1,
        value:'CompA',
        text:'Cheerfull'
        },
        {
        id:2,
        value:'CompB',
        text:'Romantic'
        },
        {
        id:3,
        value:'CompC',
        text:'Gloomy'
        },
        {
        id:4,
        value:'CompD',
        text:'Angry'
        },
      ]
    }
  },
}
</script>

<template>
  <div class="h-screen ">
    <AppHeader></AppHeader>
    <div class=" w-[80%] mx-auto text-xl">
      <div class="flex justify-around items-center">
        <div class=" rounded-2xl  flex flex-col justify-start items-center">
          <h1 class="text-2xl mt-4 mb-4 text-[#212529] font-semibold">{{title}}</h1>
            <div class="mb-4">
              <select class="min-w-96 text-center font-bold box" v-model="activeComponent" >
                <option class="font-bold  " v-for="value in values" :key="value.id" :value="value.value"> {{value.text}}</option>
              </select>
            </div>
            <div>
              <Transition name="fade" mode="out-in">
              <component :is="activeComponent"></component>
              </Transition>
            </div>
        </div>
      </div>
    </div>
  </div>

</template>

<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.box{
    width:13rem;
    height:2rem;
    border: 1px solid #000;
    border-radius: 4px;
    color:#212529
}
</style>
