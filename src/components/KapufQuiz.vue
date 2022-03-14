<template>
    <div class="full-height">
        <div class="is-flex advice-container flip-2-hor-top-1">
            <div class="advice">
            <h1>Random Advice</h1>
            <p class="advice-text">{{post.slip.advice}}</p>
            </div>
        </div>
            <a v-on:click="refreshAdvice" class="button">New Advice</a>
    </div>
</template>

<script>
    import axios from 'axios'

    export default {
        name: 'kapuf-quiz',
        data: ()=> {
            return {
                post: "",
                errors: ""
            }
        },
        methods: {
            getAdvices () {
                axios.get('https://api.adviceslip.com/advice')
                .then(response => (this.post = response.data))
            },
            refreshAdvice (){
               this.getAdvices() 
            }
        },
       created () {
            this.getAdvices ();
        }
    }
</script>

<style scoped>
    h1,p { color: rgb(42, 38, 73); }
    .advice-text {
        font-size: 3rem;
        text-align: center;
    }
    .full-height {
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }
    .is-flex {
        display: flex;
        flex-direction: column;
        text-align: center;
    }
    .advice-container {
        background-color: rgba(183, 207, 241, 0.705);
        width: 60%;
        padding: 30px;
        border-radius: 14px;
        
    }
    .flip-2-hor-top-1 {
	-webkit-animation: flip-2-hor-top-1 0.5s cubic-bezier(0.455, 0.030, 0.515, 0.955) both;
	        animation: flip-2-hor-top-1 0.5s cubic-bezier(0.455, 0.030, 0.515, 0.955) both;
    }
    .button {
        padding: 10px 12px;
        background-color: rgb(25, 43, 92);
        margin-top: 2em;
        font-size: x-large;
        color: white;
        border-radius: 8px;
        cursor: pointer;
        transition: all 0.3s;
    }

    .button:hover {
        background-color: rgb(184, 204, 231);
        transition: 0.3s;
        color:black
    }

    
</style>