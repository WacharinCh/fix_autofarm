<template>
    <div v-if="show" class=" w-screen h-screen flex justify-center items-end ">
        <div class="w-full h-[100px] flex justify-center items-center">
            <div class="w-auto h-[100px] bg-black/50 mb-[50px] flex items-center rounded-lg">
                <div class="flex w-[100px]  justify-around ">
                    <Card :itemName="main[0].label" :img="main[0].image" :count="main[0].count" :limit="main[0].limit"/>
                </div>
                <div class="flex w-[80px]  justify-around">
                    <Icon name="material-symbols:play-arrow" class=" text-[50px] text-white" />
                </div>
                <div class="flex h-[90px] items-center gap-2 pr-[10px] ">
                    <Card itemName="ขนมปัง" img="https://picsum.photos/200" count="5" limit="30"/>
                    <Card itemName="ขนมปัง" img="https://picsum.photos/200" count="5" limit="30"/>
                    <Card itemName="ขนมปัง" img="https://picsum.photos/200" count="5" limit="30"/>
                </div>
            </div>
        </div>
        <NuxtLink to="/about">
             About page
        </NuxtLink>
    </div>
</template>

<script setup>

    const show = ref(false)
    const main = ref([{"count":61,"label":"ขนมปัง","weight":1,"image":"nui://esx_inventoryhud/html/img/items/bread.png","usable":true,"limit":100,"rare":0,"name":"bread","canRemove":1}])
    const bonus= ref([])

   onMounted(( )=>{ 
    window.addEventListener('message', (event) => {
    if (event.data.action === 'show') {
        show.value = true;
        main.value = event.date.main
        bonus.value = event.date.bonus
    }else if(event.data.action === 'update'){

    }else{
        show.value = false;
    }
});
   })
   

</script>

<style scoped></style>