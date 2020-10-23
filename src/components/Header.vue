<template>
    <div class="container">
        <div class="progress">
            <div class="progress-bar bg-success" role="progressbar" :style="{width:(propsItemCount/propsMaxItem)*100 + '%'}" aria-valuemin="0" aria-valuemax="10">
                <span v-if="propsItemCount == 0"></span>
                <span v-else>{{ propsItemCount }}/{{ propsMaxItem }}</span>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Header',
    props: ['propsMaxItem', 'propsItemCount'],
}
</script>

<style>

</style>