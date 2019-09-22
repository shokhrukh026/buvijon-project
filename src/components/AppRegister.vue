<template>
    <div class="container">
        <div class="row">
            <div class="col-md-6 offset-md-3">
                <form>
                    <div class="form-group col-md-8">
                        <label for="inputEmail4">Email</label>
                        <input type="email" class="form-control" placeholder="Email" v-model="email">
                    </div>
                    <div class="form-group col-md-8">
                        <label for="inputFirstName">First Name</label>
                        <input type="text" class="form-control" placeholder="First Name" v-model="firstName">
                    </div>
                    <div class="form-group col-md-8">
                        <label for="inputLastName">Last Name</label>
                        <input type="text" class="form-control" placeholder="Last Name" v-model="lastName">
                    </div>
                    <div class="form-group col-md-8">
                        <label for="inputPhone">Phone</label>
                        <input type="text" class="form-control" placeholder="Phone" v-model.number="phone">
                    </div>
                </form>
                <div class="d-inline-flex mb-5">
                    <span class="mr-2 ml-3 mt-2">Guests</span> 
                    <button class="btn btn-primary" @click="addGuest()"><span class="h4">+</span></button>
                </div>
                <form>
                    <div class="form-group col-md-8" v-for="(guest, index) in guests" :key="index">
                        <label for="inputGuest" @dblclick="deleteGuest(index)">Guest {{index + 1}}</label>
                        <input type="text" class="form-control" :placeholder="'Guest' + ' ' +  (index + 1)"
                        v-model="guestsInput[index]">
                    </div>
                </form>
                <hr>
                <button class="btn btn-success">Send Data</button>


                <div class="mt-5">
                    <h2>All Done!</h2>
                    <table class="table table-bordered">
                        <tbody>
                            <tr>
                                <td>Email</td>
                                <td>{{ email }}</td>
                            </tr>
                            <tr>
                                <td>Name</td>
                                <td>{{ fullName }}</td>
                            </tr>
                            <tr>
                                <td>Phone</td>
                                <td>{{ phone }}</td>
                            </tr>
                            <tr>
                                <td>Guests</td>
                                <td>
                                    <ul v-for="(guest, index) in guestsInput" :key="index">
                                        <li>{{guest}}</li>
                                    </ul>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                
                <!-- <div v-for="(guests, index) in guestsInput" :key="index">{{guestsInput[index]}}</div> -->
            </div>
        </div>
    </div>
</template>




<script>
    export default {
        data(){
            return{
                email: '',
                firstName: '',
                lastName: '',
                phone: '',
                guests: [],
                guestsInput: [],
            }
        },
        computed: {
            fullName(){
                return this.firstName + ' ' + this.lastName
            }
        },
        methods: {
            addGuest(){
                this.guests.push(1)
            },
            deleteGuest(index){
                this.guests.splice(index, 1)
            },
        }
    }
</script>



<style scoped>

</style>