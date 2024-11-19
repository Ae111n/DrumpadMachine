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
            <div id="sound-name">
                {{ currentSound }}
            </div>
            <div id="slider">
                <input v-model="currentVolume" type="range" id="volume-fader" class="volume-fader" name="volume" min="0"
                    max="1" value="1" step="0.1" oninput="setUserVolume(this.value)">
            </div>
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
            },
            currentSound: '...',
            currentVolume: '1'
        }
    },
    mounted() {
        window.addEventListener("keydown", this.onKeyDown)
    },
    methods: {
        playSound(soundName) {
            let audio = new Audio(this.sounds[soundName])
            audio.volume = this.currentVolume
            audio.load()
            audio.play(),
                this.currentSound = soundName
        },
        setUserVolume(n) {

        },
        clickButton(ref) {
            ref.focus()
            ref.click()
        },
        onKeyDown(e) {

            if (e.key === 'q' || e.key === 'Q') {
                this.clickButton(Q)
            }

            else if (e.key === 'w' || e.key === 'W') {
                this.clickButton(W)
            }
            else if (e.key === 'e' || e.key === 'E') {
                this.clickButton(E)
            }
            else if (e.key === 'a' || e.key === 'A') {
                this.clickButton(A)
            }
            else if (e.key === 's' || e.key === 'S') {
                this.clickButton(S)
            }
            else if (e.key === 'd' || e.key === 'D') {
                this.clickButton(D)
            }
            else if (e.key === 'z' || e.key === 'Z') {
                this.clickButton(Z)
            }
            else if (e.key === 'x' || e.key === 'X') {
                this.clickButton(X)
            }
            else if (e.key === 'c' || e.key === 'C') {
                this.clickButton(C)
            }
        }
    }
    ,
}
</script>

<style>
* {
    background-color: dimgray;
}

#drum-machine {
    border: 5px solid black;
    border-radius: 5px;
    width: 800px;
    height: 360px;
    display: flex;
    flex-direction: row;
    margin: 150px auto;
    background-color: rgb(238, 129, 19);
}

#pads {
    background-color: rgb(238, 129, 19);
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    width: 369px;
    height: 290px;
    font: bold;
    margin: auto;
}

.drum-pad {
    width: 100px;
    flex: 0 0 113px;
}

.drum-pad {
    appearance: button;
    background-color: #000;
    background-image: none;
    border: 1px solid #000;
    border-radius: 4px;
    box-shadow: #fff 4px 4px 0 0, #000 4px 4px 0 1px;
    box-sizing: border-box;
    color: #fff;
    cursor: pointer;
    display: inline-block;
    font-family: ITCAvantGardeStd-Bk, Arial, sans-serif;
    font-size: 14px;
    font-weight: 700;
    line-height: 20px;
    margin: 0 10px 11px 0;
    overflow: visible;
    padding: 12px 40px;
    text-align: center;
    text-transform: none;
    touch-action: manipulation;
    user-select: none;
    -webkit-user-select: none;
    vertical-align: middle;
    white-space: nowrap;
}

.drum-pad:focus {
    text-decoration: none;
}

.drum-pad:hover {
    text-decoration: none;
}

.drum-pad:active {
    box-shadow: rgba(0, 0, 0, .125) 0 3px 5px inset;
    outline: 0;
}

.drum-pad:not([disabled]):active {
    box-shadow: #fff 2px 2px 0 0, #000 2px 2px 0 1px;
    transform: translate(2px, 2px);
}

@media (min-width: 768px) {
    .drum-pad {
        padding: 12px 50px;
    }
}

#display {
    width: 350px;
    height: 300px;
    margin: auto;
    display: flex;
    flex-direction: column;
    background-color: rgb(238, 129, 19);
}

#sound-name {
    font-size: 28px;
    font-family: sans-serif;
    background-color: #2b2b2b;
    color: rgb(252, 249, 249);
    box-shadow: rgba(0, 0, 0, 0.56) 2px 6px 22px 7px;
    margin: auto;
    border-radius: 5px;
    width: 180px;
    height: 80px;
    display: flex;
    align-items: center;
    justify-content: center;
}

#slider {
    margin: auto;
    background-color: rgb(238, 129, 19);
}

.volume-fader {
    -webkit-appearance: none;
    width: 50%;
    height: 10px;
    width: 200px;
    background: #000;
    outline: none;
    border: 1px solid rgb(211, 208, 208);
    border-radius: 1px;
}

.volume-fader::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    width: 12px;
    height: 40px;
    background: #000;
    cursor: pointer;
    border: 1px solid rgb(211, 208, 208);
    border-radius: 1px;
}
</style>