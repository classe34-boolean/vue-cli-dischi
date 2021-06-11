<template>
    <div class="loader">
        <div class="text">{{ message }}</div>
         <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32">
            <path d="M18 13 L26 2 8 13 14 19 6 30 24 19 Z" />
        </svg>  
        <div class="text">Loading...</div>
    </div>
</template>

<script>
export default {
    name: "Loader",
    props: [ "message" ]
}
</script>

<style lang="scss" scoped>
    .loader {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: white;
        color: black;

        svg {
            width: 100px;
            margin: 20px 0;
            animation: pulse .5s linear infinite alternate;
        }

        .text {
            font-size: 20px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
    }

    @keyframes pulse {
        from {
            transform: scale(1);
        }
        to {
            transform: scale(1.5);
        }
    }
</style>