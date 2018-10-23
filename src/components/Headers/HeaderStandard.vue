<template>
<header>
    <div id="logo"></div>
    <div id="promo"></div>
    <div id="profile"></div>
</header>
</template>

<script>
export default {
    name: 'HeaderStandard'
}
</script>

<style lang="scss" scoped>
header {
    align-items: center;
    border: 1px solid red;
    display: flex;
    justify-content: space-between;
    padding: 1rem;
}

#logo {
    background-color: gainsboro;
    height: 120px;
    width: 240px;
}

#promo {
    background-color: gainsboro;
    height: 100px;
    width: 400px;
}

#profile {
    background-color: gainsboro;
    height: 90px;
    width: 180px;
}
</style>