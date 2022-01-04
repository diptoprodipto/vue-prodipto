<template>
  <div style="background-color: #F2F2F2; height: auto">

    <header>

        <nav style="background-color: white;" class="navbar navbar-expand-lg navbar-light fixed-top">
            <div class="container-fluid">
                <a href="#" class="navbar-brand">
                    <!-- <img src="images/logo.svg" height="28"> -->
                    <h3 class="text-danger">FlightForYou.Com</h3>
                </a>
                <button type="button" class="navbar-toggler" data-bs-toggle="collapse" data-bs-target="#navbarCollapse">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarCollapse">
                    <div class="navbar-nav ms-auto">
                        <li class="nav-item nav-link dropdown">
                            <a style="color: black; text-decoration: none;" class="" data-toggle="dropdown" href="#">Offers
                            <span class="caret"></span></a>
                            
                        </li>
                        <li class="nav-item nav-link dropdown">
                            <a style="color: black; text-decoration: none;" class="" data-toggle="dropdown" href="#">Manage
                            <span class="caret"></span></a>
                            
                        </li>
                        <li class="nav-item nav-link dropdown">
                            <a style="color: black; text-decoration: none;" class="" data-toggle="dropdown" href="#">Experience
                            <span class="caret"></span></a>
                            
                        </li>

                        <li class="nav-item nav-link dropdown">
                            <a style="color: black; text-decoration: none;" class="" data-toggle="dropdown" href="#">Marco Polo Club
                            <span class="caret"></span></a>
                            
                        </li>

                        <li class="nav-item nav-link dropdown">
                            <a style="color: black; text-decoration: none;" class="" data-toggle="dropdown" href="#">Business
                            <span class="caret"></span></a>
                            
                        </li>
                    
                        
                    </div>
                </div>
            </div>
        </nav>

    </header>


    <section style="padding: 20px">

        <h3 style="margin-top: 80px;">Ready for your next trip? Book with us now.</h3>

        <div class="row">
            <div class="col-lg-8">
                
                
                <div class="row bg-light p-4" style="height: auto">

                    <div class="col-lg-12">
                        <label style="color: #6EA1B3">Redeem Flights</label><label style="margin-left: 40px; color: #6EA1B3">Multi-city / stopover</label> 
                    </div>
                    <div class="col-lg-12">
                        <div class="row">
                            <div class="col-lg-3 border border-primary p-2" data-bs-toggle="modal" data-bs-target="#myModal">
                                <p>Leaving from</p>
                                <h1>{{leavingIata}}</h1>
                                <h4>{{leavingCity}}</h4>
                            </div>
                            <div class="col-lg-3 border border-primary p-2" data-bs-toggle="modal" data-bs-target="#myModal">

                                <p>Going to</p>
                                <h1>{{destinationIata}}</h1>
                                <h4>{{destinationCity}}</h4>
                            </div>
                            <div class="col-lg-3 border border-primary p-2" data-bs-toggle="modal" data-bs-target="#datePickerModal">

                                <p>Departing on</p>
                                <h6>{{dates.in}}</h6>
                                <hr/>
                                <p>Returning on</p>
                                <h6>{{dates.out}}</h6>
                            </div>
                            <div class="col-lg-3 border border-primary p-2">

                                <p>Leaving from</p>
                                <h1>HKG</h1>
                                <h4>Hong Kong</h4>
                            </div>
                        </div>
                    </div>
                    
                </div>
                <div class="row mt-5" style="background-color: #005E64; height: auto; border-radius: 3px">
                    <div class="col-lg-3" style="background-color: red; height: 100px">

                    </div>
                    <div class="col-lg-3" style="background-color: green; height: 100px">
                        
                    </div>
                    <div class="col-lg-3" style="background-color: blue; height: 100px">
                        
                    </div>

                    <div class="col-lg-3" style="background-color: aqua; height: 100px">
                        
                    </div>
                </div>
            </div>
            <div class="col-lg-4">
                
            </div>
        </div>

    </section>

    
  <div class="modal fade" id="myModal">
    <div class="modal-dialog">
      <div class="modal-content">

        <!-- Modal Header -->
        <div class="modal-header">
          <h4 class="modal-title">Select a departure city</h4>
          <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
        </div>

        <!-- Modal body -->
        <div class="modal-body">
          <label for="leavingInput" class="form-label">LEAVING FROM</label>
          <input type="text" class="form-control" id="leavingInput" v-model="leavingName" @input="getLeavingData"/>
          <br/>
          <label for="goingInput" class="form-label">Going to</label>
          <input type="text" class="form-control" id="goingInput" v-model="destinationName" @input="getDestinationData"/>
        </div>

        <div v-if="airportLeavingData.length > 0">
              <div @click="setState(airport)" class="p-2" style="background-color: white; border-radius: 3px; border: 1px gray solid;" v-for="airport in airportLeavingData" :key="airport.id">
                  <p>{{airport.city}} - {{airport.name}}</p>
              </div>
        </div>

        <div v-if="airportDestinationData.length > 0">
              <div @click="setDestinationState(airport)" class="p-2" style="background-color: white; border-radius: 3px; border: 1px gray solid;" v-for="airport in airportDestinationData" :key="airport.id">
                  <p>{{airport.city}} - {{airport.name}}</p>
              </div>
        </div>

      </div>
    </div>
  </div>

  <div class="modal fade" id="datePickerModal" > 
    <div class="modal-dialog" >
      <div class="modal-content">

        <div class="modal-header">
            <h4 class="modal-title">Select your travel dates</h4>
            <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
        </div>

        <div id="datepickerId" class="modal-body">

            <div class="row">
              <div class="col p-2" style="height: auto">

                <p>Departing on</p>
                <h6>{{dates.in}}</h6>

              </div>
              <div class="col p-2" style="height: auto">
                <p>Returning on</p>
                <h6>{{dates.out}}</h6>
              </div>
            </div>

            <HotelDatePicker @check-in-changed="checkIn" @check-out-changed="checkOut"></HotelDatePicker>
            
        </div>

      </div>
        
    </div>
  </div>

    

    
    
  </div>

  
  

</template>

<script>

import axios from "axios";
import HotelDatePicker from 'vue-hotel-datepicker'
import 'vue-hotel-datepicker/dist/vueHotelDatepicker.css';


export default {
  name: 'HelloWorld',
  components: {
    HotelDatePicker,
  },
  data () {
    return {
      leavingName: "",
      destinationName: '',
      leavingCity: '',
      destinationCity: '',
      leavingIata: '',
      destinationIata: '',
      airportLeavingData: [],
      airportDestinationData: [],
      dates: {
        in: null,
        out: null
      }
    }
  },
  methods: {
    getLeavingData() {
        
        console.log(this.leavingName.length)

        if(this.leavingName.length === 0){
            
            this.airportLeavingData = []
            
        }
        
        if(this.leavingName.length !== 0){
            axios.get("https://api.sharetrip.net/api/v1/flight/search/airport?name=" + this.leavingName)
            .then(res => {
                this.airportLeavingData = []
                this.airportLeavingData = res.data.response
            })
            .catch((err) => {
                console.log(err)
            });
        }
        
    },

    getDestinationData(){

        if(this.destinationName.length === 0){
            
            this.airportDestinationData = []
            
        }
        
        if(this.destinationName.length !== 0){
            axios.get("https://api.sharetrip.net/api/v1/flight/search/airport?name=" + this.destinationName)
            .then(res => {
                console.log(res.data.response)
                this.airportDestinationData = []
                this.airportDestinationData = res.data.response
            })
            .catch((err) => {
                console.log(err)
            });
        }

    },

    setState(airport){
        
        this.leavingName = airport.name
        this.leavingCity = airport.city
        this.leavingIata = airport.iata
        this.airportLeavingData = []
    },

    setDestinationState(airport){
        this.destinationName = airport.name
        this.destinationCity = airport.city
        this.destinationIata = airport.iata
        this.airportDestinationData = []
    },

    checkIn(val) {

      let checkInDate = val.toString()

      checkInDate = checkInDate.split(" ")

      this.dates.in = `${checkInDate[2]} ${checkInDate[1]} ${checkInDate[3]}`;
    },

    checkOut(val) {
      let checkOutDate = val.toString()

      checkOutDate = checkOutDate.split(" ")
     
      this.dates.out = `${checkOutDate[2]} ${checkOutDate[1]} ${checkOutDate[3]}`;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
