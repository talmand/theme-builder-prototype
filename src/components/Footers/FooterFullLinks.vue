<template>
<footer>
    <div id="links"></div>
    <div id="icons"></div>
</footer>
</template>

<script>
export default {
    name: 'FooterFullLinks'
}
</script>

<style lang="scss" scoped>
footer {
    border: 1px solid black;
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    padding: 1rem;
}

#links {
    background-color: gainsboro;
    height: 30px;
    margin-bottom: 1rem;
    width: 100%;
}

#icons {
    background-color: gainsboro;
    height: 50px;
    width: 200px;
}
</style>