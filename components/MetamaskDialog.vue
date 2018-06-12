<template>
  <v-dialog content-class="metamask-dialog" v-model="dialog" persistent width="450">
    <v-card>
      <v-btn class="close-btn" fab small absolute @click.native.stop="dialog = false">
        <v-icon color="white" size="21">close</v-icon>
      </v-btn>
      <v-card-title class="metamask-dialog__title">
        <img class="metamask-dialog__logo" src="@/assets/img/metamask.png" />
        <!-- <div class="metamask-dialog__logo">
        </div> -->
        <earth-icon class="metamask-dialog__earth-icon" />
      </v-card-title>
      <v-card-text class="metamask-dialog__text">
        <p class="metamask-dialog__headline">Plugin required</p>
        <p>Puttyimage upload requires Metamask to work. Please switch to chrome and install Metamask extension.</p>
        <p class="red--text">Remember to keep your seed words safe!</p>
        <v-btn block class="text-capitalize metamask-dialog__btn" color="orange" dark large target="_blank"
          href="https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn"
        >
          Install Metamask
        </v-btn>
        <v-btn block class="text-capitalize metamask-dialog__btn" color="teal darken-2" dark large  @click.native="dialog = false">
          Done! Installed
        </v-btn>
        <v-btn block class="text-capitalize" color="teal darken-2" flat @click.native="dialog = false">
          Connect to Ledger wallet
        </v-btn>
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
import EarthIcon from '@/assets/icons/earth.svg';

export default {
  name: 'metamask-dialog',
  components: {
    EarthIcon,
  },
  data: () => {
    const checkPlguinInstalled = () => true;
    return {
      dialog: checkPlguinInstalled(),
    };
  },
};
</script>

<style lang="scss">
/* v-dialog content-class not work for scoped css */
.metamask-dialog {
  overflow-y: visible;
}
</style>

<style lang="scss" scoped>
.close-btn {
  margin-left: -20px;
  margin-top: -20px;
  background: linear-gradient(2700deg, #6A282E, #3D286E);
}
.metamask-dialog__title {
  justify-content: center;
  background: linear-gradient(270deg, #ED8526, #EEBE78);
  height: 55px;
}
.metamask-dialog__logo {
  margin-top: -30px;
}
.metamask-dialog__earth-icon {
  height: 21px;
  position: absolute;
  right: 18px;
  width: 21px;
}
.metamask-dialog__text {
  font-size: 16px;
  margin-top: 20px;
  text-align: center;
}
.metamask-dialog__headline {
  font-size: 38px;
}
.metamask-dialog__btn {
  font-size: 18px;
}
</style>
