<template>
 
    <div class="containerAbout">
        <h1>Who are we?</h1>
        <div class="containerImg">
            <img src="https://tubers.uk/wp-content/uploads/2018/01/Who-are-we.jpg" alt="">
        </div>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam ut facere incidunt, consequatur inventore earum aut aliquam ipsum iste doloribus, quo ratione a suscipit magni quaerat! Unde rerum pariatur modi.</p>
    </div>
    
</template>

<script>
export default{
    name: "About",
}
</script>

<style lang="scss" scoped>
.containerAbout{
    background-color: white;
    width: 900px;
    margin: 90px 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    p{
        padding: 10px;
    }
}

</style>