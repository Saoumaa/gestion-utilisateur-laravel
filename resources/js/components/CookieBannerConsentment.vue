<template>

<p :class="isDisplayed ? 'block' : 'hidden' ">

by continuing to browse this site , you consent to our use of cookies to improve your online experience. 

<a href="#"> Learn more</a>

 <button type="button" @click="handelCookieStorageApproval">OK</button>

 </p>

</template>

<style scoped>

 .hidden {

 		display: none;

 }

 .block {

  display : block;
 }


</style>

<script>

	import Cookies from 'js-cookie';


export default {

	data() {

	return {

	isDisplayed: false
	}
	},
	
	methods : {


	handelCookieStorageApproval() {

	Cookies.set('user_has_agree_to_cookie_storage', 'true', { expires: 10 });

	this.isDisplayed  = false;
		


	}


	},

	mounted() {
	 if (Cookies.get('user_has_agree_to_cookie_storage') === undefined) {

	 this.isDisplayed = true;



	 }

	}


}

</script>

 