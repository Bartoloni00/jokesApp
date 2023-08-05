<template>
    <section>
        <form>
            <div>
                <label for="name">Nombre</label>
                <input type="text" :value="nombre" @input="onInputNombre" placeholder="Nombre">
            </div>
            <div>
                <label for="apellido">Apellido</label>
                <input type="text" :value="apellido" @input="onInputApellido" placeholder="apellido">
            </div>
        </form>
        
        <div>
            <img src="../assets/Abraham.jpg" alt="fotografia epica de Abraham Bartoloni">
            <p>"{{ broma }}"</p>
        </div>
        <button @click="consultarFrase">Nueva frase</button>
    </section>
</template>
<style scoped>
    section{
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    form{
        display:flex;
        justify-content: center;
        align-items: center;
        max-width: 520px;
        width: 95vw;
        /* flex-wrap: wrap; */
    }
    form>div{
        /* border:1px solid #fff; */
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding:10px;
    }
    input{
        padding: .5em;
        max-width: 40vw;
        margin-top: .5em;
        border: none;
    /* outline: 2px solid #FFA500; */
        color: #1A183E;
        font-weight: bolder;
        font-size: .9em;
        border-radius: 4px;
        text-align: center;
    }
    div{
        width: 520px;
        border-radius: 4px;
        padding: 2em;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    img{
        max-height: 130px;
        clip-path: circle(50%);
    }
    p{
        padding: 2em 0;
        font-size: 1em;
        font-weight: bolder;
        max-width: 400px;
    }
    button{
        background: #FFA500;
        border: 2px solid #fff0;
        border-radius: 4px 0;
        color: #000;
        font-size: 1.2em;
        font-weight: bolder;
        padding: .5em 2em;
        transition: all .3s;
        cursor:pointer;
        margin-bottom: 3em;
    }
    button:hover{
        border: 2px solid #FFA500;
        background: none;
        color: #FFA500;
    }
    @media (max-width: 520px) {
        div{
            width: 100%;
        }
        form>div{
            width: 100%;
        }
        /* label[for="apellido"]{
        margin-top: 1em;
        } */
        input{
            width: 100%;
        }
    }
</style>
<script>
    export default {
        data(){
            return{
                broma:'',
                nombre:'Abraham',
                apellido:'Bartoloni',
            }
        },
        created: function(){
            this.consultarFrase();
        },
        methods: {
            onInputNombre(e){
                e.target.value
                this.nombre = e.target.value
            },
            onInputApellido(e){
                this.apellido = e.target.value
            },
            consultarFrase(){
                fetch("https://api.chucknorris.io/jokes/random")
                // fetch('https://api.chucknorris.io/jokes/random?category=movie')
                    .then(res => {
                    if (!res.ok) {
                        throw new Error('Network response was not ok');
                    }
                    return res.json();
                    })
                    .then(data => {
                    let replaceName = data.value.replace(/\bChuck\b/g, this.nombre);//remplazo el nombre
                    let replaceLastName = replaceName.replace(/\bNorris\b/g, this.apellido);//remplazo el apellido
                    this.traducirFrase(replaceLastName);
                    // this.broma = replaceLastName;
                    })
                    .catch(err => {
                    console.error('Fetch error:', err);
                    });
            },
            traducirFrase(frase){
                fetch(`https://api.mymemory.translated.net/get?q=${frase}&langpair=en|es`)
                .then(res => res.json())
                .then(data => {
                    //console.log(data.responseData.translatedText);
                    this.broma = data.responseData.translatedText;
                })
                .catch(err => {
                    console.error('error de traducción:', err);
                });
            }
        }
    }
    /*
    categorias de la api de chuck norris:
    "animal",
    "dev",
    "explicit",
    "food",
    "history",
    "money",
    "movie",
    "music",
    "political",
    "religion",
    "science",
    "sport",
    "travel"
    */
</script>