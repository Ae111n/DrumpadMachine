<template >
    <div id="drum-machine" 
    @keydown.q="clickQ"
    @keydown.w="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-2.mp3')"
    @keydown.e="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-3.mp3')"
    @keydown.a="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-4_1.mp3')"
    @keydown.s="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-6.mp3')"
    @keydown.d="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/Dsc_Oh.mp3')"
    @keydown.z="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/Kick_n_Hat.mp3')"
    @keydown.x="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/RP4_KICK_1.mp3')"
    @keydown.c="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/Cev_H2.mp3')"
    >

        <div id="pads">
            <button @click="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-1.mp3')" ref="Q"  class="drum-pad"
                id="Q">Q</button>
            <button @click="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-2.mp3')"
                class="drum-pad" id="W">W</button>
            <button @click="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-3.mp3')"
                class="drum-pad" id="E">E</button>
            <button @click="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-4_1.mp3')"
                class="drum-pad" id="A">A</button>
            <button @click="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-6.mp3')"
                class="drum-pad" id="S">S</button>
            <button @click="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/Dsc_Oh.mp3')"
                class="drum-pad" id="D">D</button>
            <button @click="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/Kick_n_Hat.mp3')"
                class="drum-pad" id="Z">Z</button>
            <button @click="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/RP4_KICK_1.mp3')"
                class="drum-pad" id="X">X</button>
            <button @click="play('https://cdn.freecodecamp.org/testable-projects-fcc/audio/Cev_H2.mp3')"
                class="drum-pad" id="C">C</button>

        </div>

        <div id="display">

        </div>

    </div>
</template>

<script>
export default {
    data() {
        return {
            audio: new Audio("")

        }
    },
    methods: {
        play(link) {
            let audio = new Audio(link)
            audio.load()
            audio.play()
        },
        clickQ() {
           
                this.$refs.Q.click()
            
        },

    }
,


}
</script>

<style>
#drum-machine {
    border: 1px solid black;
    width: 900px;
    height: 400px;
    display: flex;
    flex-direction: row;
    margin: auto;
}

#pads {
    border: 1px solid red;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    width: 400px;
    height: 400px;
  
    font: bold;

}

.drum-pad {
    width: 100px;
    flex: 0 0 113px;
    margin: 10px;
}

#display {
    border: 1px solid green;
    width: 450px;
    height: 350px;
    margin: auto;
}









button {
  align-items: center;
  appearance: none;
  background-color: #8787a2;
  border-radius: 4px;
  border-width: 0;
  box-shadow: rgba(45, 35, 66, 0.4) 0 2px 4px,rgba(45, 35, 66, 0.3) 0 7px 13px -3px,#D6D6E7 0 -3px 0 inset;
  box-sizing: border-box;
  color: #36395A;
  cursor: pointer;
  display: inline-flex;
  font-family: "JetBrains Mono",monospace;
  height: 100px;
  justify-content: center;
  line-height: 1;
  list-style: none;
  overflow: hidden;
  padding-left: 16px;
  padding-right: 16px;
  position: relative;
  text-align: left;
  text-decoration: none;
  transition: box-shadow .15s,transform .15s;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  white-space: nowrap;
  will-change: box-shadow,transform;
  font-size: 18px;
}

button:focus {
  box-shadow: #D6D6E7 0 0 0 1.5px inset, rgba(45, 35, 66, 0.4) 0 2px 4px, rgba(45, 35, 66, 0.3) 0 7px 13px -3px, #D6D6E7 0 -3px 0 inset;
}

button:hover {
  box-shadow: rgba(45, 35, 66, 0.4) 0 4px 8px, rgba(45, 35, 66, 0.3) 0 7px 13px -3px, #D6D6E7 0 -3px 0 inset;
  transform: translateY(-2px);
}

button:active {
  box-shadow: #D6D6E7 0 3px 7px inset;
  transform: translateY(2px);
}
</style>