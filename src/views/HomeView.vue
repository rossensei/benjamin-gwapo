<script setup>
import { ref } from 'vue'
import Button from '../components/Button.vue'
import MessageBox from '../components/MessageBox.vue'
import Card from '../components/Card.vue'

const regularMessage = ref('')
const happyMessage = ref('')
const sadMessage = ref('')
const angryMessage = ref('')

const isRegularBtnClicked = ref(false);
const isHappyBtnClicked = ref(false);
const isSadBtnClicked = ref(false);
const isAngryBtnClicked = ref(false);

function regularBtnIsClicked() {
  isRegularBtnClicked.value = true;
}
function happyBtnIsClicked() {
  isHappyBtnClicked.value = true;
}
function sadBtnIsClicked() {
  isSadBtnClicked.value = true;
}
function angryBtnIsClicked() {
  isAngryBtnClicked.value = true;
}

function getRegularMessage(ev) {
  regularMessage.value = ev.target.value
}
function getHappyMessage(ev) {
  regularMessage.value = ev.target.value
}
function getSadMessage(ev) {
  regularMessage.value = ev.target.value
}
function getAngryMessage(ev) {
  regularMessage.value = ev.target.value
}
</script>

<template>
  <div class="w-full min-h-screen">
    <main>
      <div class="max-w-7xl mx-auto">
        <div class="py-12">
          <div class="flex justify-center items-center">
            <div class="w-[500px] border border-gray-400 rounded-md">
              <div class="p-2 border-b border-gray-400">
                <h2 class="text-sm font-normal">Alampayan, Marven</h2>
              </div>
              <div class="space-y-4 p-2">
                <div>
                  <h1 class="text-xl font-semibold">Buttons</h1>

                  <div class="flex items-center space-x-2">
                    <Button type="regular" @click="regularBtnIsClicked">Regular</Button>
                    <Button type="happy" @click="happyBtnIsClicked">Happy</Button>
                    <Button type="sad" @click="sadBtnIsClicked">Sad</Button>
                    <Button type="angry" @click="angryBtnIsClicked">Angry</Button>
                  </div>
                </div>

                <div>
                  <h1 class="text-xl font-semibold">Message Box</h1>

                  <div class="w-full grid grid-cols-2 gap-2">
                    <MessageBox :class="{ 'bg-blue-600' : isRegularBtnClicked }" class="text-sm text-white p-2" placeholder="Enter your message..." @keyup.enter="getRegularMessage"/>
                    <MessageBox :class="{ 'bg-green-500' : isHappyBtnClicked }" class="text-sm text-white p-2" placeholder="Enter your message..." @keyup.enter="getHappyMessage" />
                    <MessageBox :class="{ 'bg-yellow-400' : isSadBtnClicked }" class="text-sm text-white p-2" placeholder="Enter your message..." @keyup.enter="getSadMessage"/>
                    <MessageBox :class="{ 'bg-red-600' : isAngryBtnClicked }" class="text-sm text-white p-2" placeholder="Enter your message..." @keyup.enter="getAngryMessage"/>
                  </div>
                </div>

                <div>
                  <h1 class="text-xl font-semibold">Cards</h1>

                  <div class="w-full grid grid-cols-2 gap-2">
                    <Card type="regular" :message="regularMessage" />
                    <Card type="happy" :message="happyMessage" />
                    <Card type="sad" :message="sadMessage" />
                    <Card type="angry" :message="angryMessage" />
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>
