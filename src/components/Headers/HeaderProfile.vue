<template>
<header>
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
    border: 1px solid gainsboro;
    display: flex;
    justify-content: flex-end;
    padding: 1rem;
}

#profile {
    background-color: gainsboro;
    height: 90px;
    width: 180px;
}
</style>