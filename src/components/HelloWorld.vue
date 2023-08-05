<template>
  <h1>{{ msg }}</h1>
  <section>
    <div class="text">
      <h2>Bromas con Sello Personal</h2>
      <p>
        <strong>¡Bienvenido a nuestro Generador de Bromas!</strong> Aquí, la risa es garantizada. 
        <em>¿Estás listo para soltar carcajadas sin parar?</em> 
        ¡Pues has llegado al lugar perfecto! <strong>Nuestra aplicación, desarrollada con la potencia de Vue.js,
         utiliza la legendaria API de Chuck Norris para brindarte las bromas más ingeniosas y sorprendentes.</strong>
      </p>
      <p>
        Lo mejor de todo es que <strong>puedes personalizar cada broma con el nombre que desees.</strong>
         ¿Quieres que sea tu mejor amigo, tu hermana, o incluso tu mascota? ¡Lo hacemos posible!
          Y no solo eso, una vez que personalices la broma, 
          <strong>la traducimos al español para que puedas disfrutarla con todo su humor intacto</strong>, gracias a la API MyMemory.
      </p>
      <p>
          ¿Por qué conformarte con risas tímidas cuando puedes tener una explosión de 
          diversión con nuestro Generador de Bromas?
      </p>
      
    </div>
    <div>
      <img src="../assets/home-img.png" alt="joker frente a una ruleta">
    </div>
    <div class="text">
      <h2>¿Cómo funciona?</h2>
      <ol>
        <li>Ingresa el nombre y apellido que desees en lugar de "Abraham Bartoloni".</li>
        <li>Presiona el botón <span>"Nueva frase"</span>.</li>
        <li>¡Listo! <strong>La broma se adaptará con el nombre que proporcionaste y estará traducida al español</strong> para una experiencia aún más divertida.</li>
      </ol>
    <p>¡Prepárate para compartir risas con tus amigos y familiares!</p>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  section{
    display: flex;
    justify-content: space-evenly;
    align-items: flex-start;
    text-align: left;
    flex-wrap: wrap;
  }
  section>div{
    max-width: 400px;
  }
  div:first-of-type>p{
    padding: .5em 0;
  }
  .text{
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    margin-top: 3em;
  }
  h2{
    color: #FFA500;
  }
  div:last-of-type ol{
    margin: 3em 0;
  }
  div:last-of-type ol li{
    margin: 1em 0;
  }
  div:last-of-type ol li span{
    color: #FFA500;
    font-weight: bolder;
  }
  div:last-of-type>p{
    color: #FFA500;
  }
  @media (max-width: 920px){
    section{
          padding-bottom: 2em;
        }
  }
  @media (max-width: 520px) {
        p{
          margin: 0 1em;
        }
        img{
          max-width: 100%;
        }
        ol{
          text-align: center;
        }
    }
</style>
