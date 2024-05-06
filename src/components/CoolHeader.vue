<template>
    <h1>marrowbuster</h1>
</template>

<style scoped>
    h1 {
        text-shadow: 0 1px 0 #999, 0 2px 0 #999,
            -1px 3px 0 #888, -1px 4px 0 #888,
            -2px 5px 0 #777, -2px 6px 0 #777,
            -3px 7px 0 #666, -3px 8px 0 #666,
            -3px 9px 0 #555, -3px 10px 0 #555,
            -4px 11px 0 #444, -4px 12px 0 #444,
            -4px 10px 30px rgba(0, 0, 0, 0.5);
        color: #EEE;
        font-size: 84px;
        letter-spacing: 0.1em;
        -webkit-text-stroke: 0.1px #222;
        margin: 0;
        text-align: center;
    }

    @media screen and (max-width: 992px) {
        h1 {
            font-size: 10vw;
        }
    }
</style>