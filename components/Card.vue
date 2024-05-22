<template>
    <div class=" max-w-[80px] min-w-[80px] h-[80px] bg-green-500 rounded-lg ">
        <img :src="props.img" alt="รูปไอเทม">
        <div class=" text-[15px]"> {{props.itemName}} {{ props.count }}/{{ props.limit }} </div>
    </div>
</template>

<script setup>
    const props =  defineProps(
        [ "itemName" , "count" , "limit" , "img" ]
    )
</script>

<style lang="scss" scoped></style>