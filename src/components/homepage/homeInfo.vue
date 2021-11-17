<template>
    <section class="homeInfo">
        <div class="homeText">
            <h1 style="font-size: 20px; font-weight: 600;"> Need A Hand ? </h1>
            <h2 style="font-size: 40px; font-weight: 200;"> What You Can Do </h2>
        </div>
            <div v-if="profile.loggedIn">
            <div class="homeInfoContainer">
                <div>
                    <div>
                        <div class="textCon">
                            <img src='https://res.cloudinary.com/risidio/image/upload/v1637162043/RisidioMarketplace/Groupe_17296_smc1up.svg'/>
                            <p style="font-size: 16px; font-weight: 700;"> Upload and mint your NFT <br/><br/></p>
                            <p style="font-weight: 200;"> Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                            Molestiae iure a culpa sed quidem totam reiciendis deleniti
                            deserunt nisi, quod quam aliquid modi eveniet velit voluptates
                            nemo ipsum corporis molestias.</p>
                        </div>
                        <div class='buttonCon'><button class='button'> Upload </button></div>
                    </div>
                </div>
                <div>
                    <div>
                        <div class="textCon">
                            <img src='https://res.cloudinary.com/risidio/image/upload/v1637162044/RisidioMarketplace/002-distributed_ledger_b4tq2s.svg'/>
                            <p style="font-size: 16px; font-weight: 700;"> Sell your work <br/><br/></p>
                            <p style="font-weight: 200;"> Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                            Molestiae iure a culpa sed quidem totam reiciendis deleniti
                            deserunt nisi, quod quam aliquid modi eveniet velit voluptates
                            nemo ipsum corporis molestias.</p>
                        </div>
                        <div class='buttonCon'><button class='button'> My NFTs </button></div>
                    </div>
                </div>
                <div>
                    <div>
                        <div class="textCon">
                        <img src='https://res.cloudinary.com/risidio/image/upload/v1637162045/RisidioMarketplace/009-coin_ojj2mp.svg'/>
                            <p style="font-size: 16px; font-weight: 700;"> Buy and trade NFTs <br/><br/></p>
                            <p style="font-weight: 200;"> Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                            Molestiae iure a culpa sed quidem totam reiciendis deleniti
                            deserunt nisi, quod quam aliquid modi eveniet velit voluptates
                            nemo ipsum corporis molestias  quidem totam reiciendis d  quidem totam reiciendis d.</p></div>
                        </div>
                        <div class='buttonCon'><button class='button'> Gallery </button>
                    </div>
                </div>
            </div>
        </div>
        <div v-else>
            <div class="homeInfoContainer">
                <div>
                    <img src='https://res.cloudinary.com/risidio/image/upload/v1634828295/RisidioMarketplace/Screenshot_2021-10-21_at_15.57.57_q7chjf.png'/>
                    <p style="font-size: 16px; font-weight: 700;"> Connect your wallet <br/><br/></p>
                    <p style="font-weight: 200;"> Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                    Molestiae iure a culpa sed quidem totam reiciendis deleniti
                    deserunt nisi, quod quam aliquid modi eveniet velit voluptates
                    nemo ipsum corporis molestias.</p>
                    <button class='button'> Something </button>
                </div>
                <div>
                    <img src='https://res.cloudinary.com/risidio/image/upload/v1634828295/RisidioMarketplace/Screenshot_2021-10-21_at_15.57.57_q7chjf.png'/>
                    <p style="font-size: 16px; font-weight: 700;"> Upload and mint your NFT <br/><br/></p>
                    <p style="font-weight: 200;"> Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                    Molestiae iure a culpa sed quidem totam reiciendis deleniti
                    deserunt nisi, quod quam aliquid modi eveniet velit voluptates
                    nemo ipsum corporis molestias.</p>
                    <div class='buttonCon'><button class='button'> Something </button></div>
                </div>
                <div>
                    <img src='https://res.cloudinary.com/risidio/image/upload/v1634828295/RisidioMarketplace/Screenshot_2021-10-21_at_15.57.57_q7chjf.png'/>
                    <p style="font-size: 16px; font-weight: 700;"> Sell your work <br/><br/></p>
                    <p style="font-weight: 200;"> Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                    Molestiae iure a culpa sed quidem totam reiciendis deleniti
                    deserunt nisi, quod quam aliquid modi eveniet velit voluptates
                    nemo ipsum corporis molestias.</p>
                    <div class='buttonCon'><button class='button'> Something </button></div>
                </div>
                <div>
                    <div>
                        <img src='https://res.cloudinary.com/risidio/image/upload/v1634828295/RisidioMarketplace/Screenshot_2021-10-21_at_15.57.57_q7chjf.png'/>
                        <p style="font-size: 16px; font-weight: 700;"> Buy and trade NFTs <br/><br/></p>
                        <p style="font-weight: 200;"> Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                        Molestiae iure a culpa sed quidem totam reiciendis deleniti
                        deserunt nisi, quod quam aliquid modi eveniet velit voluptates
                        nemo ipsum corporis molestias  quidem totam reiciendis d  quidem totam reiciendis d.</p>
                        <div class='buttonCon'><button class='button'> Something </button></div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
  name: 'HomeInfo',
  props: ['profile']
}
</script>

<style lang="scss" scoped>
.homeInfo{
    min-height: 1000px;
    background: transparent linear-gradient(180deg, rgba(34, 14, 149, 1) 0%, rgba(7, 23, 100, 1) 100%) 0% 0% no-repeat padding-box;
    padding: 5%;
    color: white;
    text-align: center;
}
.homeText > * {
  color:white;
  max-width: 800px;
  margin: 30px auto
}
.textCon{
    min-height: 400px;
}
.homeInfoContainer{
    margin-top: 100px;
    display: flex;
    flex-wrap: wrap;
}
.homeInfoContainer > * {
    flex-direction: row;
    flex: 1 1 400px;
    padding: 20px 50px;
    text-align: center;
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
        max-width: 420px;
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
  padding: 15px 70px;
  border-radius: 100px;
  border: none;
  background: rgba(255, 255, 255, 0.2);
  font-size: 14px;
  font-weight:700;
  color: rgba(95, 189, 193, 1);
}
.button:hover{
    background: rgba(255, 255, 255, 0.3);
}
</style>
