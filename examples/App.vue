<template lang="html">
  <div class="helvetica tc pa4">
    <h1 class="f4 silver">currentBreakpoint: {{$mq}}</h1>
    <h1>{{$mq | mq({ sm: 'small and medium', lg: 'large'})}}</h1>
    <div class="center measure-wide tc">
      <mq-layout mq="lg">
        <prism language="html" code="&lt;mq-layout mq=&quot;lg&quot;&gt; only large &lt;/mq-layout&gt;"/>
      </mq-layout>
      <mq-layout mq="md+">
        <prism language="html" code="&lt;mq-layout mq=&quot;md+&quot;&gt; md and larger &lt;/mq-layout&gt;"/>
      </mq-layout>
      <mq-layout :mq="['sm','lg']">
        <prism language="html" code="&lt;mq-layout mq=&quot;['sm', 'lg']&quot;&gt; sm and lg &lt;/mq-layout&gt;"/>
      </mq-layout>
    </div>
    <!-- <button @click="setMQ">set MQ to sm</button> -->
  </div>
</template>

<script>
import Vue from 'vue'

export default {
	components: {
		Prism: window.PrismComponent
	},

	beforeCreate() {
		Vue.prototype.$setPoint('sm')
	}
}
</script>

<style lang="css">
</style>
