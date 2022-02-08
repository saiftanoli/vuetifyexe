<template>
<div>
    <v-container>
        <v-row justify="center">
            <v-form ref="form" lazy-validation v-model="valid">
                <v-text-field :counter="10" :rules="nameRules" required v-model="name" label="name"></v-text-field>
                <v-text-field :rules="emailRules" required v-model="email" label="email"></v-text-field>
                <v-text-field :rules="passwordRules" required v-model="password" type="password" label="password"></v-text-field>
                <v-select :rules="selectRules"  :items="items" v-model="select" label="item" required></v-select>
                <v-checkbox :rules="checkRules" required label="Do you agree" v-model="checkbox" ></v-checkbox>
                <v-btn :disabled="!valid" class="mr-4" @click="validate" color="success">Validate</v-btn>
                <v-btn class="mr-4" @click="reset" color="eror">Reset form</v-btn>
                <v-btn class="mr-4" @click="resetValidate" color="warning">Reset Validate</v-btn>
            </v-form>
        </v-row>

    </v-container>
</div>
</template>

<script>
export default {
    name: 'Form',
    data() {
        return {
            valid:true,
            
            name: '',
            nameRules:[
                v => !! v || 'name is required',
                v =>  (v && v.length <=10) || 'number must be less than 10 chracters'
            ],
            email:'',
            emailRules:[
                v => !! v || 'email is required',
                 v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
            ],
            select:null,
            selectRules: [v => !! v || 'item  is required'],
            checkRules: [v => !! v || 'you must agree to continue'],
            items:['app','web','graphics','data structure'],
            password:'',
            passwordRules:[
                v => !! v || 'password is required',
                v => (v && v.length <=8) || 'password must be less than 10 chracters'
            ],
            checkbox:false,
        }
    },
    methods:{
        validate(){
            this.$refs.form.validate()
        },
        reset(){
            this.$refs.form.reset()
        },
        resetValidate(){
            this.$refs.form.resetValidate()
        }
    }
}
</script>

<style lang="scss" scoped>

</style>
