<template>
    <section class="homeInfo">
        <div class="homeText">
            <h1> Lorem ipsum dolor sit amet, consect </h1>
            <h2> Lorem ipsum dolor sit amet </h2>
            <p> Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                Molestiae iure a culpa sed quidem totam reiciendis deleniti
                deserunt nisi, quod quam aliquid modi eveniet velit voluptates
                nemo ipsum corporis molestias.</p>
        </div>
        <div class="homeInfoContainer">
            <div>
                <img src='https://res.cloudinary.com/risidio/image/upload/v1634828295/RisidioMarketplace/Screenshot_2021-10-21_at_15.57.57_q7chjf.png'/>
                <p> Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                Molestiae iure a culpa sed quidem totam reiciendis deleniti
                deserunt nisi, quod quam aliquid modi eveniet velit voluptates
                nemo ipsum corporis molestias.</p>
                <button class='button'> Something </button>
            </div>
            <div>
                <img src='https://res.cloudinary.com/risidio/image/upload/v1634828295/RisidioMarketplace/Screenshot_2021-10-21_at_15.57.57_q7chjf.png'/>
                <p> Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                Molestiae iure a culpa sed quidem totam reiciendis deleniti
                deserunt nisi, quod quam aliquid modi eveniet velit voluptates
                nemo ipsum corporis molestias.</p>
                <button class='button'> Something </button>
            </div>
            <div>
                <img src='https://res.cloudinary.com/risidio/image/upload/v1634828295/RisidioMarketplace/Screenshot_2021-10-21_at_15.57.57_q7chjf.png'/>
                <p> Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                Molestiae iure a culpa sed quidem totam reiciendis deleniti
                deserunt nisi, quod quam aliquid modi eveniet velit voluptates
                nemo ipsum corporis molestias.</p>
                <button class='button'> Something </button>
            </div>
            <div>
                <div>
                <img src='https://res.cloudinary.com/risidio/image/upload/v1634828295/RisidioMarketplace/Screenshot_2021-10-21_at_15.57.57_q7chjf.png'/>
                <p> Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                Molestiae iure a culpa sed quidem totam reiciendis deleniti
                deserunt nisi, quod quam aliquid modi eveniet velit voluptates
                nemo ipsum corporis molestias  quidem totam reiciendis d  quidem totam reiciendis d.</p></div>
                <div class='buttonCon'><button class='button'> Something </button></div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
  name: 'HomeInfo'
}
</script>

<style lang="scss" scoped>
.homeInfo{
    min-height: 1000px;
    background: transparent linear-gradient(180deg, #220E95 0%, #071764 100%) 0% 0% no-repeat padding-box;
    padding: 5%;
    color: white;
    text-align: center;
}
.homeText > * {
  color:white;
  max-width: 800px;
  margin: 30px auto
}

.homeInfoContainer{
    margin-top: 100px;
    display: flex;
    flex-wrap: wrap;
}
.homeInfoContainer > * {
    flex-direction: row;
    flex: 1 1 300px;
    padding: 20px 50px;
    text-align: justify;
    img{
        border-radius: 10px;
        display: block;
        margin:20px auto;
        max-width: 100%;
        max-height: 300px;
    }
    p{
        font-size: .9em;
        display: block;
        margin:auto;
        color: white;
        max-width: 320px;
    }
}
.buttonCon{
    height: 70px;
    display: block;
    margin-top: auto auto 0 auto;
}
.button{
  display: flex;
  margin: auto auto 0 auto;
  padding: 15px 30px;
  border-radius: 100px;
  border: none;
  background-color: rgb(0, 177, 201);
  font-size: 14px;
  font-weight:700;
  color: white;
}
</style>
