<template>
    <div :class="className">
        <slot />
    </div>
</template>
<script>
export default {
    props: {
        className: {
        type: String,
        default: 'box'
        },
     }
}
</script>