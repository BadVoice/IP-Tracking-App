<template>
    <div class="absolute  
    top-1/4 left-1/2
    transform -translate-x-1/2 -translate-y-1/2
    flex 
    flex-col 
    lg:flex-row 
    bg-white
    gap-y-4
    gap-x-12
    px-8 pt-8 pb-12
    rounded-md
    ">
    <!-- Flex Item #1 -->
        <div class="flex flex-col ">
            <h3 class="text-xs mb-2 uppercase">IP Address</h3>
            <span class="text-2xl">{{ipInfo.address}}</span>
        </div>
        <!-- Flex Item #2 -->
        <div class="flex flex-col ">
            <h3 class="text-xs mb-2 uppercase">Location</h3>
            <span class="text-2xl">{{ipInfo.state}}</span>
        </div>
        <!-- Flex Item #3 -->
        <div class="flex flex-col ">
            <h3 class="text-xs mb-2 uppercase">Timezone</h3>
            <span class="text-2xl">{{ipInfo.timezone}}</span>
        </div>
        <!-- Flex Item #4 -->
        <div class="flex flex-col ">
            <h3 class="text-xs mb-2 uppercase">Ips</h3>
            <span class="text-2xl">{{ipInfo.isp}}</span>
        </div>
    </div>
</template>

<script setup>
    props: ['ipInfo']
</script>

<style lang="scss" scoped>

</style>