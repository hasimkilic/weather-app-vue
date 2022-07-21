<script>
export default{
    data(){
        return{
            title:'Weather By Mood'
        };
    },
}
</script>

<template>
    <header class="w-100">
        <div class="h-[4rem] flex justify-center items-center shadow-sm shadow-slate-300 text-[#076585] text-4xl font-bold">
           {{title}}
        </div>
    </header>
</template>