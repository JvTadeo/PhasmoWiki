<template>
    <div class="ghost-card-content">
        <div class="header-info">
            <p id="header">{{ ghost.name }}</p>
            <div class="ghost-evidence">
                <p v-for="(evidence, index) in ghost.evidences" :key="index" >{{evidence}}</p>                
            </div>
            <div class="ghost-attack-speed">
                <p>{{ ghost.attackSanity }}</p>
                <p>Steps</p>
            </div>
        </div>
        <div class="ghost-information">
            <div class="ghost-scroll">
                <div class="ghost-tittle-tips" v-if="ghost.tips != null">
                    <i>Dicas</i>
                </div>
                <ul v-if="ghost.tips != null" id="list-tips">
                    <li v-for="(tips, index) in ghost.tips" :key="index">{{ tips }}</li> <!-- Tips -->
                </ul>
                <div class="ghost-tittle-tips" v-if="ghost.behaviors != null">
                    <i>Comportamentos</i>
                </div>
                <ul v-if="ghost.behaviors != null" id="list-tips">
                     <li v-for="(tips, index) in ghost.behaviors" :key="index">{{ tips }}</li> <!-- Behaviors -->
                </ul>
                <div class="ghost-tittle-tips" v-if="ghost.abilities != null">
                    <i>Habilidade</i>
                </div>
                <ul v-if="ghost.abilities != null" id="list-tips">
                    <li v-for="(tips, index) in ghost.abilities" :key="index">{{ tips }}</li> <!-- Abilites -->
                </ul>
                <div class="ghost-tittle-tips" v-if="ghost.huntSpeed != null">
                    <i>Velocidade de Caçada</i>
                </div>
                <ul v-if="ghost.huntSpeed != null" id="list-tips">
                    <li v-for="(tips, index) in ghost.huntSpeed" :key="index">{{ tips }}</li> <!-- Hunt Speed -->
                </ul>
                <div class="ghost-tittle-tips" v-if="ghost.huntSanity != null">
                    <i>Sanidade de Caçada</i>
                </div>
                <ul v-if="ghost.huntSanity != null" id="list-tips">
                    <li v-for="(tips, index) in ghost.huntSanity" :key="index">{{ tips }}</li> <!-- Sanity -->                    
                </ul>
                <div class="ghost-tittle-tips" v-if="ghost.evidence != null">
                    <i>Evidência</i>
                </div>
                <ul v-if="ghost.evidence != null" id="list-tips">
                    <li v-for="(tips, index) in ghost.evidence" :key="index">{{ tips }}</li> <!-- Evidence -->                    
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:"GhostCard",
    props: ['ghost'],
}
</script>

<style scoped>

@import url('https://fonts.cdnfonts.com/css/lazy-dog');

.ghost-card-content{
    background-color: #FCEFC0;        
    box-shadow: inset 0 0 25px #968570;      
    display: flex;
    flex-direction: column;
    align-items: center;
    max-width: 350px;        
    max-height: 500px;
    margin-bottom: 12px;   
    border-radius: 12px;  
    overflow: hidden; 
    color: #141414;
}
.header-info{
    display: flex;
    flex-direction: column;
    width: 100%;
    justify-content: center;
    align-items: center;
    text-align: center;    
}

#header{
    margin: 28px 0px;
    font-size: 44px;
    font-weight: 300;
    font-family: 'Lazy Dog', sans-serif;
}
.ghost-evidence, .ghost-attack-speed{    
    text-align: center;
    display: flex;
    justify-content: space-around;
    align-items: center;
}

.ghost-evidence{    
    margin: 8px 0px; 
    font-size: 14px;
    width: min-content;
}

.ghost-evidence p{    
    padding: 2px 14px;                
}

.ghost-attack-speed{            
    width: 90%;
    margin-bottom: 8px;
}

.ghost-information{
    display: flex;
    margin: 0px 12px 12px 12px;
    background-color: rgba(0, 0, 0, 0.15);
    box-shadow: inset 0 0 12px rgb(0, 0, 0, 0.35);
    width: 90%;    
    border-radius: 14px;    
}

.ghost-scroll{
    overflow-y: scroll;
    display: flex;
    flex-direction: column;
    align-items: flex-start;    
    justify-content: flex-start;    
    height: 200px;
    padding: 12px;
}

.ghost-scroll ul {
  list-style-type: disc; /* Remove os marcadores de lista */
  padding-left: 28px;
}

.ghost-scroll li {
  margin-bottom: 10px; /* Adiciona espaço entre os itens da lista, opcional */
}

.ghost-tittle-tips{    
    display: flex;
    width: 100%;
    text-align: left;
    font-weight: 500;    
}

/* width */
::-webkit-scrollbar {
  width: 5px;  
}

/* Track */
::-webkit-scrollbar-track {
  background: none;  
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: rgb(0, 0, 0, 0.25);
  border-radius: 4px;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #555;
}
</style>
