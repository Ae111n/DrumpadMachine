<template>
    <div id="drum-machine">



        <div id="pads">
            <button @click="playSound('heater1')" ref="Q" class="drum-pad" id="Q">Q</button>
            <button @click="playSound('heater2')" ref="W" class="drum-pad" id="W">W</button>
            <button @click="playSound('heater3')" ref="E" class="drum-pad" id="E">E</button>
            <button @click="playSound('heater4')" ref="A" class="drum-pad" id="A">A</button>
            <button @click="playSound('clap')" ref="S" class="drum-pad" id="S">S</button>
            <button @click="playSound('openHH')" ref="D" class="drum-pad" id="D">D</button>
            <button @click="playSound('kickNHat')" ref="Z" class="drum-pad" id="Z">Z</button>
            <button @click="playSound('kick')" ref="X" class="drum-pad" id="X">X</button>
            <button @click="playSound('closedHH')" ref="C" class="drum-pad" id="C">C</button>

        </div>

        <div id="display">

        </div>

    </div>
</template>

<script>
export default {
    data() {
        return {
            sounds: {
                heater1: "https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-1.mp3",
                heater2: "https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-2.mp3",
                heater3: "https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-3.mp3",
                heater4: "https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-4_1.mp3",
                clap: "https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-6.mp3",
                openHH: "https://cdn.freecodecamp.org/testable-projects-fcc/audio/Dsc_Oh.mp3",
                kickNHat: "https://cdn.freecodecamp.org/testable-projects-fcc/audio/Kick_n_Hat.mp3",
                kick: "https://cdn.freecodecamp.org/testable-projects-fcc/audio/RP4_KICK_1.mp3",
                closedHH: "https://cdn.freecodecamp.org/testable-projects-fcc/audio/Cev_H2.mp3"
            }

        }
    },
    mounted() {
        window.addEventListener("keydown", this.onKeyDown)
    },
    methods: {
        playSound(soundName) {
            let audio = new Audio(this.sounds[soundName])
            audio.load()
            audio.play()
        },


        clickk(ref) {
           ref.focus()
           ref.click()
           
        },

        onKeyDown(e) {

            if (e.key === 'q' || e.key === 'Q') {
                this.clickk(Q)
            }

            else if (e.key === 'w' || e.key === 'W') {
                this.clickk(W)
            }
            else if (e.key === 'e' || e.key === 'E') {
                this.clickk(E)
            }
            else if (e.key === 'a' || e.key === 'A') {
                this.clickk(A)
            }
            else if (e.key === 's' || e.key === 'S') {
                this.clickk(S)
            }
            else if (e.key === 'd' || e.key === 'D') {
                this.clickk(D)
            }
            else if (e.key === 'z' || e.key === 'Z') {
                this.clickk(Z)
            }
            else if (e.key === 'x' || e.key === 'X') {
                this.clickk(X)
            }
            else if (e.key === 'c' || e.key === 'C') {
                this.clickk(C)
            }

        }
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

.drum-pad {
    align-items: center;
    appearance: none;
    background-color: #8787a2;
    border-radius: 4px;
    border-width: 0;
    box-shadow: rgba(45, 35, 66, 0.4) 0 2px 4px, rgba(45, 35, 66, 0.3) 0 7px 13px -3px, #D6D6E7 0 -3px 0 inset;
    box-sizing: border-box;
    color: #36395A;
    cursor: pointer;
    display: inline-flex;
    font-family: "JetBrains Mono", monospace;
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
    transition: box-shadow .15s, transform .15s;
    user-select: none;
    -webkit-user-select: none;
    touch-action: manipulation;
    white-space: nowrap;
    will-change: box-shadow, transform;
    font-size: 18px;
}

.drum-pad:focus {
    transform: translateY(2.9px);
    outline: none;
    box-shadow: #D6D6E7 0 0 0 2px inset, rgba(45, 35, 66, 0.4) 0 2px 4px, rgba(45, 35, 66, 0.3) 0 7px 13px -3px, #D6D6E7 0 -3px 0 inset;
}

.drum-pad:hover {
    box-shadow: rgba(45, 35, 66, 0.4) 0 4px 8px, rgba(45, 35, 66, 0.3) 0 7px 13px -3px, #D6D6E7 0 -3px 0 inset;
    transform: translateY(-2px);
}

.drum-pad:active {
    box-shadow: #D6D6E7 0 3px 7px inset;
    transform: translateY(2px);
}

</style>