<template>
    <div class="myAlgoConnection">
        <div>
            <button v-if="!addrToUse" class="right button button-primary" v-on:click="connectToMyAlgo()" ><span>Connect to myAlgo</span></button>
        </div>
        <div class="picker" v-if="pressed">
            <p>Which address would you like to use ?</p>
            <ul>
            <li v-for="address in addresses" :key="address"><input type="radio" v-model="addrToUse" :id="address" :value="address">{{ address }}</li>
            </ul>
            <button class="center" v-on:click="returnAddress()">Done</button>
        </div>
        <div class="showaddress" v-if="addrToUse && !pressed">
            <button v-on:click="pressed=!pressed">Change address</button>
            <br />
            <button class="right button-primary" v-on:click="addrToUse=''">Disconnect</button>
        </div>
    </div>
</template>


<script> 
import MyAlgo from '@randlabs/myalgo-connect';
const myAlgoWallet = new MyAlgo();

export default {
    name: "myAlgoConnection",
    data() {
        return {
            addrToUse: '',
            addresses: [],
            pressed: false
        }
    },
    methods: {
        connectToMyAlgo: async function () {
            try {
                const accounts = await myAlgoWallet.connect();
                console.log(accounts)
                this.addresses = accounts.map(account => account.address);
                } catch (err) {
                console.error(err);
                }
            if (this.pressed == false) {
                this.pressed = !this.pressed
            }
        },
        returnAddress: function () {
            this.$emit('clicked', this.addrToUse)
            this.pressed = !this.pressed
        }
    }

}
</script>

<style scoped>

.right {
    float: right;
}

.center {
    float: center;
}

.picker {
    border-radius: 4px;
    border: 1px solid rgb(0, 0, 0);
    background-color: rgb(228, 222, 222);
    padding: 15px;
    right: 50px;
    opacity: 90%;
    position: fixed;
    text-align: center;
}

.myAlgoConnection {
    color: #000;
    padding: 10px;
    /* position: absolute; */
    /* top: 5%;
    right: 5%; */
}

.showaddress {
    font-size: 0.8em;
}


ul {
    list-style-type: none;
}

li {
    padding-left: none;
    font-size: 0.8em;
}


/* Popup container */
.popup {
  color: #33C3F0;
  position: relative;
  display: inline-block;
  cursor: pointer;
}
/* Actual popup text */
.popup .popuptext {
  visibility: hidden;
  width: 600px;
  background-color: #555;
  color: #fff;
  text-align: left;
  border-radius: 6px;
  padding: 8px 8px;
  position: absolute;
  z-index: 1;
  bottom: -75%;
  left: 50%;
  margin-left: -50px;
}
/* Code in popup */
.popup code {
  background-color: inherit;
  border-style: hidden;
  border-radius: 6px;
  padding: 10px;
}
/* Popup arrow */
/* .popup .popuptext::after {
  content: "";
  position: absolute;
  top: 100%;
  left: 50%;
  margin-left: -5px;
  border-width: 5px;
  border-style: solid;
  border-color: #555 transparent transparent transparent;
} */
/* Toggle this class when clicking on the popup container (hide and show the popup) */
.popup .show {
  visibility: visible;
  -webkit-animation: fadeIn 1s;
  animation: fadeIn 1s
}
/* Add animation (fade in the popup) */
@-webkit-keyframes fadeIn {
  from {opacity: 0;}
  to {opacity: 1;}
}

@keyframes fadeIn {
  from {opacity: 0;}
  to {opacity:1 ;}
}



</style>