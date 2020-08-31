<template>
    <div class="container">
        <form v-if="!isSubmitted">
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <h1>Form for your order</h1>
                    <hr>
                    <div class="row">
                        <div class="form-group">
                            <label for="firstName">First Name:</label>
                            <input
                                    type="text"
                                    class="form-control"
                                    id="firstName"
                                    v-model="userData.firstName">
                        </div>
                        <div class="form-group">
                            <label for="lastName">Last Name:</label>
                            <input
                                    type="text"
                                    class="form-control"
                                    id="lastName"
                                    v-model="userData.lastName">
                        </div>
                    </div>
                    <div class="row">
                        <div class="form-group">
                            <label for="email">Email:</label>
                            <input
                                    type="text"
                                    class="form-control"
                                    id="email"
                                    v-model="userData.email">
                        </div>
                    </div>
                    <div class="row">
                        <div class="form-group">
                            <label for="password">Password:</label>
                            <input
                                    type="password"
                                    class="form-control"
                                    id="password"
                                    v-model="userData.password">
                        </div>
                    </div>
                   <div class="row">
                       <p>Store data?</p>
                       <div class="form-group">
                           <label for="yes">
                               <input
                                       type="radio"
                                       id="yes"
                                       value="Yes"
                                       v-model="store"> Yes
                           </label>
                           <label for="no">
                               <input
                                       type="radio"
                                       id="no"
                                       value="No"
                                       v-model="store"> No
                           </label>
                       </div>
                   </div>

                    <!-- Exercise 1 -->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <!-- Full Name (First Name + Last Name) -->
                    <!-- Mail -->
                    <!-- Password -->
                    <!-- Store Data? Yes/No -->

                    <div class="col-xs-2 col-xs-offset-5">
                        <input
                                type="submit"
                                value="Submit"
                                @click.prevent="submitted()">
                    </div>

                    <!-- Exercise 2 -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->



                    <!-- Exercise 3 -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                </div>
            </div>
        </form>
        <div v-else class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ userData.firstName }} {{ userData.lastName }}</p>
                        <p>Mail: {{ userData.email }}</p>
                        <p>Password: {{ userData.password }}</p>
                        <p>Store in Database?: {{ store }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data: () => ({
            userData: {
                firstName: '',
                lastName: '',
                email: 'alyonium@gmail.com',
                password: '',
            },
            store: 'Yes',
            isSubmitted: false,
        }),
        methods: {
            submitted()  {
                this.isSubmitted = true;
            }
        }
    }
</script>

<style>
</style>
