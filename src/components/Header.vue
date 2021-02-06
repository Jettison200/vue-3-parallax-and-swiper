<template>
<header>
    <Nav logo='Bakkas' @add-count="add"></Nav>
<div class="header-text">
    <h1>Welcome To Janta's Law Firm</h1>
    <p>{{counter}}</p>
    

</div>

</header>  

   
</template>

<script>
import Nav from './Nav';

export default {
components:{
    Nav
 
},
data() {
    return {
        counter: 0,
        img: require('../assets/images/x.jpg')
    }
},

methods:{
    add(){
        this.counter = this.counter +1;
    }
       
},

}
</script>

<style lang="scss" scoped>
header{
    height: 100%;
    background-color: rgb(138, 219, 138);
}
.header-text{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 50%;
    width: 100%;
    h1, p{
        font-size: 60px;
    }
}

.jarallax {
    position: relative;
    z-index: 0;
}
.jarallax > .jarallax-img {
       object-fit: cover;
    /* support for plugin https://github.com/bfred-it/object-fit-images */
    font-family: 'object-fit: cover;';
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    z-index: -1;
    background-image: url('https://images.pexels.com/photos/4069613/pexels-photo-4069613.jpeg');
}
</style>