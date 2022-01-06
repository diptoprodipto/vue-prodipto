<template>
  <div style="background-color: #E6E7E9; height: auto">

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


    <section style="padding: 20px;">

        <h3 style="margin-top: 80px; padding: 0">Ready for your next trip? Book with us now.</h3>

        <div class="row">
            <div class="col-lg-8 mb-3">
                
                <div class="row bg-light p-4" style="height: auto">

                  <p class="p-0" style="font-weight: bold">Flights</p>

                  <hr>

                    <div class="col-lg-12 p-0 mb-3">
                        <label style="color: #6EA1B3">Redeem Flights</label><label style="margin-left: 40px; color: #6EA1B3">Multi-city / stopover</label> 
                    </div>
                    <div class="col-lg-12">
                        <div class="row" style="box-shadow: 5px 10px 18px #888888;">
                            <div style="height: 200px" class="col-lg-3 border border-right-primary p-4" data-bs-toggle="modal" data-bs-target="#myModal">
                                <p>Leaving from</p>
                                <h1>{{leavingIata}}</h1>
                                <h4>{{leavingCity}}</h4>
                            </div>
                            <div style="height: 200px" class="col-lg-3 border border-right-primary p-4" data-bs-toggle="modal" data-bs-target="#myModal">

                                <p>Going to</p>
                                <h1>{{destinationIata}}</h1>
                                <h4>{{destinationCity}}</h4>
                            </div>
                            <div style="height: 200px" class="col-lg-3 border border-right-primary p-4" data-bs-toggle="modal" data-bs-target="#datePickerModal">

                                <p>Departing on</p>
                                <h6>{{dates.in}}</h6>
                                <hr/>
                                <p>Returning on</p>
                                <h6>{{dates.out}}</h6>
                            </div>
                            <div style="height: 200px; background-color: #005E64;" @click="fetchWeatherData(); fetchLeavingWeatherData()" class="col-lg-3 border border-right-primary p-4 d-flex flex-column align-items-center justify-content-center text-light" data-bs-toggle="modal" data-bs-target="#weatherModal">

                                <h4>Search flights</h4>
                            </div>
                        </div>
                    </div>

                    <div class="col-lg-12 p-0 mt-3">
                        <li class="nav-item nav-link dropdown">
                            <a style="color: black; text-decoration: none;" class="dropdown-toggle" data-toggle="dropdown" href="#">Return
                            <span class="caret"></span></a>
                            
                        </li>
                        <li class="nav-item nav-link dropdown">
                            <a style="color: black; text-decoration: none;" class="dropdown-toggle" data-toggle="dropdown" href="#">Econonmy, 1 Adult
                            <span class="caret"></span></a>
                            
                        </li>
                       
                    </div>
                    
                </div>
                <div class="row mt-5 text-light" style="background-color: #005E64; height: auto; border-radius: 3px">
                    <div class="col-lg-3 d-flex flex-column align-items-center justify-content-center border-end" style="padding: 10px;">
                      <i class="bi bi-list-ul" style="font-size: 40px"></i>
                      <p>Manage Booking</p>
                    </div>
                    <div class="col-lg-3 d-flex flex-column align-items-center justify-content-center border-end" style="padding: 10px">
                      <i class="bi bi-check-circle" style="font-size: 40px;"></i>
                      
                      <p>Check in</p> 
                    </div>
                    <div class="col-lg-3 d-flex flex-column align-items-center justify-content-center border-end" style="padding: 10px;">
                      <i class="bi bi-arrow-left-right" style="font-size: 40px;"></i>
                      <p style="display: block">Rebook and refund</p>
                    </div>

                    <div class="col-lg-3 d-flex flex-column align-items-center justify-content-center" style="padding: 10px">
                      <i class="bi bi-bell" style="font-size: 40px"></i>
                      <p>COVID-19 updates</p> 
                    </div>
                </div>
            </div>
            <div class="col-lg-4">

              <img style="height: 100%; width: 100%" src="https://media.istockphoto.com/photos/tropical-island-picture-id157484556?k=20&m=157484556&s=612x612&w=0&h=m1rYX4iMPX-V0d0gPo1OEo5pCOlROiY5SF8t8TXr9NY=" class="img-fluid">
                
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

        <div class="modal-footer">
          <button type="button" class="btn btn-danger" data-bs-dismiss="modal">Done</button>
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

        <div class="modal-footer">
          <button type="button" class="btn btn-danger" data-bs-dismiss="modal">Done</button>
        </div>

      </div>
        
    </div>
  </div>

  <div v-if="bottomDiv"> 
    <div> <!---  class="modal-dialog" style="max-width: 99%;" role="document" -->
      <div>

        <div>

            <div class="p-2 bg-light">
              <p style="font-weight: bold; color: red">Select departing flight</p>
              <p><b>{{leavingCity}}</b> to <b>{{destinationCity}}</b></p>
              <p>Date: <b>{{dates.in}}</b></p>
            </div>
            

            <div class="row p-4">
              <div class="col-lg-6" style="border-right: 1px black solid">

                <div class="row">
                  <div class="col-lg-12 p-0">
                    <p>Date: <b>{{dates.in}}</b></p>
                    <p>Forecast for: <b>{{leavingCity}}</b></p>
                  </div>
                </div>

                <div class="row">

                  <div  class="col-lg-3 p-0">

                    <section class="h-auto">
                      <div>
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h5 class="mb-1">Morning</h5>
                              <h3 class="mb-1 mt-3">{{leftTemp1}} °C</h3>
                              <i class="bi bi-cloud-sun-fill" style="color: #868B94; font-size: 50px"></i>
                              <h6 class="mb-1 mt-2">{{leftRain1}}%</h6>
                            </div>

                            
                          </div>
                        </div>
                      </div>
                    </section>

                  </div>
                  <div  class="col-lg-3 p-0">

                    <section class="h-auto">
                      <div>
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h5 class="mb-1">Afternoon</h5>
                              <h3 class="mb-1 mt-3">{{leftTemp2}} °C</h3>
                              <i class="bi bi-cloud-rain" style="color: #868B94; font-size: 50px"></i>
                              <h6 class="mb-1 mt-2">{{leftRain2}}%</h6>
                            </div>

                            
                          </div>
                        </div>
                      </div>
                    </section>

                  </div>
                  <div  class="col-lg-3 p-0" >

                    <section class="h-auto">
                      <div>
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h5 class="mb-1">Evening</h5>
                              <h3 class="mb-1 mt-3">{{leftTemp3}} °C</h3>
                              <i class="bi bi-cloud-moon-fill" style="color: #868B94; font-size: 50px"></i>
                              <h6 class="mb-1 mt-2">{{leftRain3}}%</h6>
                            </div>

                            
                          </div>
                        </div>
                      </div>
                    </section>

                  </div>
                  <div  class="col-lg-3 p-0">

                    <section class="h-auto">
                      <div>
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h5 class="mb-1">Overnight</h5>
                              <h3 class="mb-1 mt-3">{{leftTemp4}} °C</h3>
                              <i class="bi bi-cloud-moon-fill" style="color: #868B94; font-size: 50px"></i>
                              <h6 class="mb-1 mt-2">{{leftRain4}}%</h6>
                            </div>

                          </div>
                        </div>
                      </div>
                    </section>

                  </div>

                </div>

              </div>

              <div class="col-lg-6">

                <div class="row">
                  <div class="col-lg-12">
                    <p>Date: <b>{{dates.out}}</b></p>
                    <p>Forecast for: <b>{{destinationCity}}</b></p>
                  </div>
                </div>

                <div class="row">

                  <div  class="col-lg-3 p-0">

                    <section class="h-auto">
                      <div>
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h5 class="mb-1">Morning</h5>
                              <h3 class="mb-1 mt-3">{{rightTemp1}} °C</h3>
                              <i class="bi bi-cloud-sun-fill" style="color: #868B94; font-size: 50px"></i>
                              <h6 class="mb-1 mt-2">{{rightRain1}}%</h6>
                            
                            </div>
                          </div>
                        </div>
                      </div>
                    </section>

                  </div>
                  <div  class="col-lg-3 p-0">

                    <section class="h-auto">
                      <div>
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h5 class="mb-1">Afternoon</h5>
                              <h3 class="mb-1 mt-3">{{rightTemp2}} °C</h3>
                              <i class="bi bi-cloud-rain" style="color: #868B94; font-size: 50px"></i>
                              <h6 class="mb-1 mt-2">{{rightRain2}}%</h6>
                            </div>
                          </div>
                        </div>
                      </div>
                    </section>

                  </div>
                  <div  class="col-lg-3 p-0" >

                    <section class="h-auto">
                      <div>
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h5 class="mb-1">Evening</h5>
                              <h3 class="mb-1 mt-3">{{rightTemp3}} °C</h3>
                              <i class="bi bi-cloud-moon-fill" style="color: #868B94; font-size: 50px"></i>
                              <h6 class="mb-1 mt-2">{{rightRain3}}%</h6>
                            </div>
                          </div>
                        </div>
                      </div>
                    </section>

                  </div>
                  <div  class="col-lg-3 p-0">

                    <section class="h-auto">
                      <div>
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h5 class="mb-1">Overnight</h5>
                              <h3 class="mb-1 mt-3">{{rightTemp4}} °C</h3>
                              <i class="bi bi-cloud-moon-fill" style="color: #868B94; font-size: 50px"></i>
                              <h6 class="mb-1 mt-2">{{rightRain4}}%</h6>
                            </div>
                          </div>
                        </div>
                      </div>
                    </section>

                  </div>
                </div>

              </div>
              
            </div>

            <div class="row p-3 mt-5">

              <div class="col-lg-12 p-1">
                <div class="row no-gutters">

                  <div class="col-lg-6">
                    <div class="row">
                    <div class="col-lg-2 col-md-6">
                        <p style="color:black ;font-size:14px;">Sort by: </p>
                    </div>
                    <div class="col-lg-2 col-md-6">
                     
                      <p style="color: blue ;font-size:14px;">Recommended</p>
                    </div>
                    <div class="col-lg-2 col-md-6">
                        
                        <p style="color: blue ;font-size:14px;">Departure time</p>
                    </div>
                    <div class="col-lg-2 col-md-6">
                        
                        <p style="color: blue ;font-size:14px;">Arrival time </p>
                    </div>
                    <div class="col-lg-2 col-md-6">
                        
                        <p style="color: blue ;font-size:14px;">Duration</p>
                    </div>
                    <div class="col-lg-2 col-md-6">
                      
                        <p style="color: blue ;font-size:14px;">Fare</p>
                    </div>
                    
                    </div>
                  </div>
                  
                </div>
              </div>

              <div class="col-lg-12">
                <div class="row">
                  <div class="col-lg-6 p-3">

                    <div class="row">
                      <div class="col-lg-12 p-0">
                        <p>3 flights found</p>
                      </div>
                      <div class="col-lg-12 bg-light p-3 mb-2">

                        <div class="row">
                          <div class="col-lg-3 d-flex flex-column justify-content-center align-items-center">

                            <h2>{{jsonData.st.start}}</h2>
                            <h6>{{leavingIata}}</h6>

                          </div>
                          <div class="col-lg-3 d-flex flex-column justify-content-center align-items-center">
                            <h6>{{jsonData.st.duration}}</h6>
                            <h6>LAX</h6>
                            
                          </div>
                          <div class="col-lg-3 d-flex flex-column justify-content-center align-items-center">

                            <h2>{{ jsonData.st.end }}</h2>
                            <h6>{{destinationIata}}</h6>
                            
                          </div>
                          <div class="col-lg-3 d-flex flex-column justify-content-center align-items-center">
                            <h6>CX880 <i class="bi bi-chevron-right"></i> CX7906</h6>
                          </div>
                        </div>
                        
                      </div>
                      <div class="col-lg-12 bg-light p-3 mb-2">

                        <div class="row">
                          <div class="col-lg-3 d-flex flex-column justify-content-center align-items-center">

                            <h2>{{ jsonData.nd.start }}</h2>
                            <h6>{{leavingIata}}</h6>

                          </div>
                          <div class="col-lg-3 d-flex flex-column justify-content-center align-items-center">
                            <h6>{{jsonData.nd.duration}}</h6>
                            <h6>LAX</h6>
                            
                          </div>
                          <div class="col-lg-3 d-flex flex-column justify-content-center align-items-center">

                            <h2>{{ jsonData.nd.end }}</h2>
                            <h6>{{destinationIata}}</h6>
                            
                          </div>
                          <div class="col-lg-3 d-flex flex-column justify-content-center align-items-center">
                            <h6>CX880 <i class="bi bi-chevron-right"></i> AA2002</h6>
                          </div>
                        </div>
                        
                      </div>
                      <div class="col-lg-12 bg-light p-3 mb-2">

                        <div class="row">
                          <div class="col-lg-3 d-flex flex-column justify-content-center align-items-center">

                            <h2>{{ jsonData.rd.start }}</h2>
                            <h6>{{leavingIata}}</h6>

                          </div>
                          <div class="col-lg-3 d-flex flex-column justify-content-center align-items-center">
                            
                            <h6>{{ jsonData.rd.duration }}</h6>
                            <h6>LAX</h6>
                            
                          </div>
                          <div class="col-lg-3 d-flex flex-column justify-content-center align-items-center">

                            <h2>{{ jsonData.rd.end }}</h2>
                            <h6>{{destinationIata}}</h6>
                            
                          </div>
                          <div class="col-lg-3 d-flex flex-column justify-content-center align-items-center">
                            <h6>CX880 <i class="bi bi-chevron-right"></i> AA2475</h6>
                          </div>
                        </div>
                        
                      </div>
                      
                    </div>

                  </div>
                  <div class="col-lg-6">

                    <div class="row">
                      <div class="col-lg-6 p-3">

                        <div class="row ml-4">
                          <div class="col-lg-12 d-flex flex-column justify-content-center align-items-center text-light" style="background-color: #005E64">
                            <p>Economy</p>
                          </div>
                          <div style="border-top: 2px #005E64 solid; " class="col-lg-12 bg-light p-3 mb-2 d-flex flex-column justify-content-center align-items-center">
                            <label>From</label>
                            <h2>{{leavingIata}}{{ jsonData.economy.price1 }}</h2>
                          </div>
                          <div style="border-top: 2px #005E64 solid; " class="col-lg-12 bg-light p-3 mb-2 d-flex flex-column justify-content-center align-items-center">
                            <label>From</label>
                            <h2>{{leavingIata}}{{ jsonData.economy.price2 }}</h2>
                          </div>
                          <div style="border-top: 2px #005E64 solid; " class="col-lg-12 bg-light p-3 mb-2 d-flex flex-column justify-content-center align-items-center">
                            <label>From</label>
                            <h2>{{leavingIata}}{{ jsonData.economy.price3 }}</h2>
                          </div>
                          
                        </div>

                      </div>
                      
                      <div class="col-lg-6 p-3">

                        <div class="row">
                          <div class="col-lg-12 d-flex flex-column justify-content-center align-items-center text-light" style="background-color: #005E64">
                            <p>Premium Economy</p>
                          </div>
                          <div style="border-top: 2px #005E64 solid; " class="col-lg-12 bg-light p-3 mb-2 d-flex flex-column justify-content-center align-items-center">
                            <label>From</label>
                            <h2>{{leavingIata}}{{ jsonData.premium.price1 }}</h2>
                          </div>
                          <div style="border-top: 2px #005E64 solid; " class="col-lg-12 bg-light p-3 mb-2 d-flex flex-column justify-content-center align-items-center">
                            <label>From</label>
                            <h2>{{leavingIata}}{{ jsonData.premium.price2 }}</h2>
                          </div>
                          <div style="border-top: 2px #005E64 solid; " class="col-lg-12 bg-light p-3 mb-2 d-flex flex-column justify-content-center align-items-center">
                            <label>From</label>
                            <h2>{{leavingIata}}{{ jsonData.premium.price3 }}</h2>
                          </div>
                        </div>
                        
                      </div>
                      
                    </div>

                  </div>
                </div>
              </div>

            </div>
            
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
import jsonData from './data.json'

export default {
  name: 'HelloWorld',
  components: {
    HotelDatePicker,
  },
  data () {
    return {
      destCountryName: '',
      leavingName: "",
      destinationName: '',
      leavingCity: 'Select',
      destinationCity: 'Select',
      leavingIata: 'SELECT',
      destinationIata: 'SELECT',
      airportLeavingData: [],
      airportDestinationData: [],
      dates: {
        in: 'Select',
        out: 'Select'
      },
      destinationDate: '',
      leavingDate: '',
      fetchedWeatherData: [],
      leftTemp1: '',
      leftTemp2: '',
      leftTemp3: '',
      leftTemp4: '',
      rightTemp1: '',
      rightTemp2: '',
      rightTemp3: '',
      rightTemp4: '',
      jsonData: jsonData,
      bottomDiv: false,
      leftRain1: '',
      leftRain2: '',
      leftRain3: '',
      leftRain4: '',
      rightRain1: '',
      rightRain2: '',
      rightRain3: '',
      rightRain4: ''
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

        let countryName = airport.name.split(',')
        this.destCountryName = countryName[0]
        
    },

    checkIn(val) {

      if(val !== null){
        console.log(val)

        let checkInDate = val.toString()

        checkInDate = checkInDate.split(" ")

        this.dates.in = `${checkInDate[2]} ${checkInDate[1]} ${checkInDate[3]}`;

        const months = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"];
        let monthIndex = months.indexOf(checkInDate[1]);

        this.leavingDate = `${checkInDate[3]}-${monthIndex+1}-${checkInDate[2]}`
      }

    },

    checkOut(val) {

      if(val !== null){
        let checkOutDate = val.toString()

        checkOutDate = checkOutDate.split(" ")
      
        this.dates.out = `${checkOutDate[2]} ${checkOutDate[1]} ${checkOutDate[3]}`;

        console.log(checkOutDate)

        const months = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"];
        let monthIndex = months.indexOf(checkOutDate[1]);

        this.destinationDate = `${checkOutDate[3]}-${monthIndex+1}-${checkOutDate[2]}`

      }
      
    },

    fetchWeatherData(){

      this.bottomDiv = true

      var options = {
          method: 'GET',
          url: 'https://weatherapi-com.p.rapidapi.com/forecast.json',
          params: {q: this.destinationCity, days: '14', dt: this.destinationDate},
          headers: {
            'x-rapidapi-host': 'weatherapi-com.p.rapidapi.com',
            'x-rapidapi-key': 'e3b89510f8mshc7703596d4ae869p189756jsn4bcc816aea37'
          }
        };

        axios.request(options).then((response) => {
          let weatherData = response.data
          let sum1, sum2, sum3, sum4, rainSum1, rainSum2, rainSum3, rainSum4
          sum1 = sum2 = sum3 = sum4 = rainSum1 = rainSum2 = rainSum3 = rainSum4 = 0
          let temp_c_1, temp_c_2, temp_c_3, temp_c_4, rain1, rain2, rain3, rain4
          temp_c_1 = temp_c_2 = temp_c_3 = temp_c_4 = rain1 = rain2 = rain3 = rain4 = []

          for(let i=0;i<weatherData.forecast.forecastday[0].hour.length;i++){
            
            if(i>=0 && i<6){
              temp_c_1 = [...temp_c_1, weatherData.forecast.forecastday[0].hour[i].temp_c]

              rain1 = [...rain1, weatherData.forecast.forecastday[0].hour[i].chance_of_rain]

            }
            else if(i>=6 && i<12){
              temp_c_2 = [...temp_c_2, weatherData.forecast.forecastday[0].hour[i].temp_c]
              rain2 = [...rain2, weatherData.forecast.forecastday[0].hour[i].chance_of_rain]
            }
            else if(i>=12 && i<18){
              temp_c_3 = [...temp_c_3, weatherData.forecast.forecastday[0].hour[i].temp_c]
              rain3 = [...rain3, weatherData.forecast.forecastday[0].hour[i].chance_of_rain]
            }
            else if(i>=18 && i<24){
              temp_c_4 = [...temp_c_4, weatherData.forecast.forecastday[0].hour[i].temp_c]
              rain4 = [...rain4, weatherData.forecast.forecastday[0].hour[i].chance_of_rain]
            }
          }

          sum1 = temp_c_1.reduce((acc, curr) => {
                  return acc + curr;
          });

          sum2 = temp_c_2.reduce((acc, curr) => {
                  return acc + curr;
          });

          sum3 = temp_c_3.reduce((acc, curr) => {
                  return acc + curr;
          });

          sum4 = temp_c_4.reduce((acc, curr) => {
                  return acc + curr;
          });

          rainSum1 = rain1.reduce((acc, curr) => {
                  return acc + curr;
          });

          rainSum2 = rain2.reduce((acc, curr) => {
                  return acc + curr;
          });

          rainSum3 = rain3.reduce((acc, curr) => {
                  return acc + curr;
          });

          rainSum4 = rain4.reduce((acc, curr) => {
                  return acc + curr;
          });

          

          this.rightTemp1 = (sum1/6).toFixed(2)
          this.rightTemp2 = (sum2/6).toFixed(2)
          this.rightTemp3 = (sum3/6).toFixed(2)
          this.rightTemp4 = (sum4/6).toFixed(2)


          this.rightRain1 = Math.round(rainSum1/6)
          this.rightRain2 = Math.round(rainSum2/6)
          this.rightRain3 = Math.round(rainSum3/6)
          this.rightRain4 = Math.round(rainSum4/6)


        }).catch ((error) => {
          console.error(error);
        });

    },

    fetchLeavingWeatherData(){
      var options = {
          method: 'GET',
          url: 'https://weatherapi-com.p.rapidapi.com/forecast.json',
          params: {q: this.leavingCity, days: '14', dt: this.leavingDate},
          headers: {
            'x-rapidapi-host': 'weatherapi-com.p.rapidapi.com',
            'x-rapidapi-key': 'e3b89510f8mshc7703596d4ae869p189756jsn4bcc816aea37'
          }
        };

        axios.request(options).then((response) => {
          console.log(response.data)
          let weatherData = response.data
          let sum1, sum2, sum3, sum4, rainSum1, rainSum2, rainSum3, rainSum4
          sum1 = sum2 = sum3 = sum4 = rainSum1 = rainSum2 = rainSum3 = rainSum4 = 0
          let temp_c_1, temp_c_2, temp_c_3, temp_c_4, rain1, rain2, rain3, rain4
          temp_c_1 = temp_c_2 = temp_c_3 = temp_c_4 = rain1 = rain2 = rain3 = rain4 = []

          for(let i=0;i<weatherData.forecast.forecastday[0].hour.length;i++){
            
            if(i>=0 && i<6){
              temp_c_1 = [...temp_c_1, weatherData.forecast.forecastday[0].hour[i].temp_c]

              rain1 = [...rain1, weatherData.forecast.forecastday[0].hour[i].chance_of_rain]

            }
            else if(i>=6 && i<12){
              temp_c_2 = [...temp_c_2, weatherData.forecast.forecastday[0].hour[i].temp_c]
              rain2 = [...rain2, weatherData.forecast.forecastday[0].hour[i].chance_of_rain]
            }
            else if(i>=12 && i<18){
              temp_c_3 = [...temp_c_3, weatherData.forecast.forecastday[0].hour[i].temp_c]
              rain3 = [...rain3, weatherData.forecast.forecastday[0].hour[i].chance_of_rain]
            }
            else if(i>=18 && i<24){
              temp_c_4 = [...temp_c_4, weatherData.forecast.forecastday[0].hour[i].temp_c]
              rain4 = [...rain4, weatherData.forecast.forecastday[0].hour[i].chance_of_rain]
            }
          }

          sum1 = temp_c_1.reduce((acc, curr) => {
                  return acc + curr;
          });

          sum2 = temp_c_2.reduce((acc, curr) => {
                  return acc + curr;
          });

          sum3 = temp_c_3.reduce((acc, curr) => {
                  return acc + curr;
          });

          sum4 = temp_c_4.reduce((acc, curr) => {
                  return acc + curr;
          });

          rainSum1 = rain1.reduce((acc, curr) => {
                  return acc + curr;
          });

          rainSum2 = rain2.reduce((acc, curr) => {
                  return acc + curr;
          });

          rainSum3 = rain3.reduce((acc, curr) => {
                  return acc + curr;
          });

          rainSum4 = rain4.reduce((acc, curr) => {
                  return acc + curr;
          });

          

          this.leftTemp1 = (sum1/6).toFixed(2)
          this.leftTemp2 = (sum2/6).toFixed(2)
          this.leftTemp3 = (sum3/6).toFixed(2)
          this.leftTemp4 = (sum4/6).toFixed(2)


          this.leftRain1 = Math.round(rainSum1/6)
          this.leftRain2 = Math.round(rainSum2/6)
          this.leftRain3 = Math.round(rainSum3/6)
          this.leftRain4 = Math.round(rainSum4/6)


        }).catch ((error) => {
          console.error(error);
        });
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
