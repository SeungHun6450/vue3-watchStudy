<template>
  <h1 @click="changeMessage">
    {{ msg }}
  </h1>
  <h1>{{ reversedMessage }}</h1>
</template>

<script>
  export default {
    data() {
      return {
        msg: 'Hello Watch?'
      }
    },
    computed: {
       reversedMessage() {
         return this.msg.split('').reverse().join('')
      }
    },
    watch: {  
      // 감시하고싶은 데이터가 있다면 watch부분에 메소드처럼 만들어 메소드의 로직으로 그 데이터가 변경됐을때 어떤 내용을 실행할 것인지를 명시해주면 된다.
      // 감시하는 데이터들이 변경되는 것을 감지할 때 실행된다.
      // 매개변수를 이용할 수 있다.
      // 데이터들의 변경사항들을 감시하는 옵션이다.
      // msg() {
      msg(v) {
        // 변경이 일어났을 때 console.log를 출력
        // console.log('msg: ', this.msg)
        console.log('msg: ', v)
      },
      // 계산된 데이터도 감시할 수 있다.
      reversedMessage() {
        console.log('reversedMessage: ', this.reversedMessage)
      }
    },
    methods: {
      // click시 msg를 'Good!'으로 변경시키는 메소드
      changeMessage() {
        this.msg = 'Good!'
      }
    }
  }
</script>

