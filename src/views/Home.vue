/* eslint-disable*/

<template>
    <div>
        <div class="container-fluid my-5">

            <div class="row">
           
                    <div  v-for="mentor in mentors" :key="mentor._id" class="col-xl-3 col-lg-6 col-md-6 col-sm-12 col-12 ">
                            <div  class="card my-5">
                                <div class="card-body text-center">
                                    <h3 class="card-title"> <a href=""> {{ mentor.name }}</a></h3>
                                                                        <p class="card-text">{{mentor.username}}</p>                              
                                    <hr>
                                    <p>{{mentor.email}}</p>
                                    <p>{{mentor.bio}}</p>
                                    <a href="{{mentor.facebook}}">Facebook</a>
                                </div>
                            </div>
                        </div>
            </div>
        </div>
    </div>
</template>
<style  scoped>
a {
  color: black;
}
hr{
    color: purple;
    width: 200px;
}
</style>
<script>
  /* eslint-disable*/

    import axios from 'axios'
    
      export default {
          data() {
            return {
              mentors: [],
            }
          },

          mounted() {
            axios
      .get('http://localhost:1300/api/')
      .then(response => (this.mentors = response.data))
        }
      }
    </script>