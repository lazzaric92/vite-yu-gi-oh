<script>
export default{
    data(){
        return {
        
        }
    }
}
</script>

<template>
    <div class="loader-wrapper">
        <p>Generating cards...</p>
        <div class="loader"></div>
    </div>
</template>

<style scoped lang="scss">
@use '../assets/styles/partials/variables' as *;

.loader-wrapper {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);

    p {
        font-size: 1.5rem;
        font-weight: bold;
        text-transform: uppercase;
        color: white;
    }
}

.loader {
    margin: 2rem auto;
    width: 40px;
    aspect-ratio: 2/3;
    animation: 
        l3-1 2s infinite linear,
        l3-2 3s infinite steps(1) -.5s;
}
@keyframes l3-1 {
    0%   {transform: perspective(150px) rotateX(  0deg) rotateY(0deg)}
    50%  {transform: perspective(150px) rotateX(180deg) rotateY(0deg)}
    100% {transform: perspective(150px) rotateX(180deg) rotateY(180deg)}
}
@keyframes l3-2 {
    0%  {background: white}
    33% {background: #a81f07}
    66% {background: $bg-darkgrey}
}
</style>