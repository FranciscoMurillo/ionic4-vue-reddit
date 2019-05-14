<template>
<ion-card>
	<ion-item>
		<ion-label position="floating">
			Hello
		</ion-label>
		<ion-input :value="greeting" @input="greeting = $event.target.value"></ion-input>
	</ion-item>
	<ion-button color="success" expand="full" @click="handleClick"> Enviar</ion-button>
</ion-card>
</template>

<script>


export default {
data(){
	return{
		greeting: ''
	}
},	

methods:{
	async handleClick() {
		const alert = await this.$ionic.alertController.create({
			header: 'Alert',
			subHeader: 'Subtitulo',
			message:  this.greeting,
			buttons: ['Ok']
		})
		await alert.present()
	}
}

}
</script>
 