<template>
<nav>
    <div class="link"></div>
    <div class="link"></div>
    <div class="link"></div>
    <div class="link"></div>
    <div class="link"></div>
    <div class="link"></div>
    <div class="link"></div>
</nav>
</template>

<script>

</script>

<style lang="scss" scoped>
nav {
    border: 1px solid blue;
    padding: 0.5rem 1rem;
}

.link {
    display: flex;
    align-items: center;
    margin: 0.5rem 0;

    &:before {
        background-color: gainsboro;
        border-radius: 100%;
        content: '';
        display: block;
        height: 1.5rem;
        margin-right: 0.5rem;
        width: 1.5rem;
    }
    &:after {
        background-color: gainsboro;
        content: '';
        display: block;
        height: 20px;
        width: 80px;
    }
}
</style>