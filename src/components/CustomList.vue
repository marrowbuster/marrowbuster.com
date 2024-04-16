<template>
    <div>
        <slot></slot>
    </div>
</template>

<style scoped>
    div {
        display: grid;
        grid-template-columns: auto 1fr;
        gap: 2px 4px;
    }

    div *:nth-child(odd) {
        justify-self: center;
    }
</style>