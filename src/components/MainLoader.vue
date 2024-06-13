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
        <div class="first-loader"></div>
        <div class="second-loader"></div>
    </div>
</template>

<style scoped lang="scss">
@use '../assets/styles/partials/variables' as *;

.loader-wrapper {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

.first-loader {
    width: fit-content;
    font-weight: bold;
    font-family: monospace;
    font-size: 30px;
    color: #0000;
    background: linear-gradient(90deg,#000000 calc(5% + 0.5ch),#a81f07 calc(50% + 0.5ch),#ffffff 0) right/calc(200% + 1ch) 100%;
    -webkit-background-clip: text;
            background-clip: text;
    animation: l7 2s infinite steps(11);
}
.first-loader:before {
    content:"Generating cards..."
}
@keyframes l7 {to{background-position: left}}

.second-loader {
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