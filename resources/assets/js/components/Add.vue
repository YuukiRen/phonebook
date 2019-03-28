<template>
	<div class="modal" :class='openmodal'>
	  <div class="modal-background"></div>
	  <div class="modal-card">
	    <header class="modal-card-head">
	      <p class="modal-card-title">Add New</p>
	      <button class="delete" aria-label="close" @click="close"></button>
	    </header>
	    <section class="modal-card-body">
	      <!-- Content ... -->
				<div class="field">
					<label class="label">Name</label>
					<div class="control">
<<<<<<< HEAD
						<input class="input" type="text" placeholder="Name" v-model="list.name">
					</div>
				</div>
				
				<div class="field">
					<label class="label">Phone</label>
					<div class="control">
						<input class="input" type="number" placeholder="Phone" v-model="list.phone">
					</div>
				</div>
				
				<div class="field">
					<label class="label">Email</label>
					<div class="control">
						<input class="input" type="email" placeholder="Email" v-model="list.email">
=======
						<input class="input" :class="{'is-danger':errors.name}" type="text" placeholder="Nama" v-model="list.name"> 
>>>>>>> 75df00ee5f0cd2592a41d27a3af3bd9c2c02d8c0
					</div>
					<small v-if="errors.name" class="has-text-danger">{{errors.name[0]}}</small>
				</div>
				<div class="field">
					<label class="label">Email</label>
					<div class="control">
						<input class="input" :class="{'is-danger':errors.email}" type="text" placeholder="Email" v-model="list.email">
					</div>
					<small v-if="errors.email" class="has-text-danger">{{errors.email[0]}}</small>
				</div>
				<div class="field">
					<label class="label">Phone</label>
					<div class="control">
						<input class="input" :class="{'is-danger':errors.phone}" type="text" placeholder="Phone" v-model="list.phone">
					</div>
					<small v-if="errors.phone" class="has-text-danger">{{errors.phone[0]}}</small>
				</div>
				<!-- Content ... -->
	    </section>
	    <footer class="modal-card-foot">
<<<<<<< HEAD
	      <button class="button is-success" @click='save'>Save changes</button>
	      <button class="button">Cancel</button>
=======
	      <button class="button is-success" @click="save">Save</button>
	      <button class="button" @click="close">Cancel</button>
>>>>>>> 75df00ee5f0cd2592a41d27a3af3bd9c2c02d8c0
	    </footer>
	  </div>
	</div>
</template>

<script>
	export default{
		props:['openmodal'],
		data(){
			return{
				list:{
					name:'',
<<<<<<< HEAD
					phone:'',
					email:''
				}
=======
					email:'',
					phone:''
				},
				errors:{}
>>>>>>> 75df00ee5f0cd2592a41d27a3af3bd9c2c02d8c0
			}
		},
		methods:{
			close(){
				this.$emit('closeRequest')
			},
			save(){
<<<<<<< HEAD
				axios.post('/phonebook',this.$data).then((response)=>console.log(response))
				.catch((error)=>console.log(error))
=======
				axios.post('/phonebook',this.$data.list)
				.then((response)=>{
					this.close()
					// this.$parent.lists.push(this.$data.list)
					this.$parent.lists.push(response.data)
					this.$parent.lists.sort(function(a,b){
						if(a.name<b.name){
							return -1;
						}
						else if(a.name>b.name){
							return 1;
						}
					})
				})
				.catch((error) => this.errors = error.response.data.errors)
>>>>>>> 75df00ee5f0cd2592a41d27a3af3bd9c2c02d8c0
			}
		}
	}
</script>