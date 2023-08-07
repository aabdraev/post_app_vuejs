<template>
    <button class="btn">
        <slot></slot>
    </button>
</template>

<script>
export default {
    name: "my-button"
}
</script>

<style scoped>
.btn {
    align-self: flex-end;
    padding: 10px 15px;
    background: none;
    border: 1px solid #353535;
    color: #353535;
}

.btn:hover {
    background-color: #e8e8e8;
}
</style>