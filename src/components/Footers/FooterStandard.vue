<template>
<footer>
    <div id="links"></div>
    <div id="icons"></div>
</footer>
</template>

<script>
export default {
    name: 'FooterStandard'
}
</script>

<style lang="scss" scoped>
footer {
    border: 1px solid black;
    display: flex;
    justify-content: space-between;
    padding: 1rem;
}

#links {
    background-color: gainsboro;
    height: 100px;
    width: 300px;
}

#icons {
    background-color: gainsboro;
    height: 50px;
    width: 200px;
}
</style>