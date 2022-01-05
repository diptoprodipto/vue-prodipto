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
                            <div style="height: 200px; background-color: #005E64;" @click="fetchWeatherData" class="col-lg-3 border border-right-primary p-4 d-flex flex-column align-items-center justify-content-center text-light" data-bs-toggle="modal" data-bs-target="#weatherModal">

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

  <div class="modal fade" id="weatherModal"> 
    <div class="modal-dialog" style="max-width: 99%;" role="document">
      <div class="modal-content ml-0">

        <div class="modal-header">
            <p>Select departing flight</p>
            
            <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
        </div>

        <div class="modal-body">
            <p>{{leavingCity}} to {{destinationCity}}</p>

            <div class="row">
              <div class="col-lg-6" style="border-right: 1px black solid">

                <div class="row" style="border-right: 1px black solid">

                  <div  class="col-lg-3 bg-danger p-0">

                    <section class="h-auto">
                      <div class="">
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h5 class="mb-1">Morning</h5>
                              <h3 class="mb-1 mt-3">{{leftTemp1}} °C</h3>
                              <i class="bi bi-sun" style="color: #868B94; font-size: 50px"></i>
                            
                            </div>

                            
                          </div>
                        </div>
                      </div>
                    </section>

                  </div>
                  <div  class="col-lg-3 bg-danger p-0">

                    <section class="h-auto">
                      <div class="">
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h5 class="mb-1">Afternoon</h5>
                              <h3 class="mb-1 mt-3">{{leftTemp2}} °C</h3>
                              <i class="bi bi-cloud" style="color: #868B94; font-size: 50px"></i>
                            
                            </div>

                            
                          </div>
                        </div>
                      </div>
                    </section>

                  </div>
                  <div  class="col-lg-3 bg-danger p-0" >

                    <section class="h-auto">
                      <div class="">
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h5 class="mb-1">Evening</h5>
                              <h3 class="mb-1 mt-3">{{leftTemp3}} °C</h3>
                              <i class="bi bi-moon" style="color: #868B94; font-size: 50px"></i>
                            
                            </div>

                            
                          </div>
                        </div>
                      </div>
                    </section>

                  </div>
                  <div  class="col-lg-3 bg-danger p-0">

                    <section class="h-auto">
                      <div class="">
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h5 class="mb-1">Overnight</h5>
                              <h3 class="mb-1 mt-3">{{leftTemp4}} °C</h3>
                              <i class="bi bi-moon" style="color: #868B94; font-size: 50px"></i>
                            
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

                  <div  class="col-lg-3 bg-danger p-0">

                    <section class="h-auto">
                      <div class="">
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            <div class="d-flex">
                              <h6 class="flex-grow-1">12:00 am</h6>
                              <h6>6:00 am</h6>
                            </div>
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h2 class="mb-1">London</h2>
                              <h5 class="mb-4">2021-12-26</h5>
                              <h5 id="degreec1" class="mb-0 font-weight-bold" style="color: #1C2331;"> High 13°C - Low 13°C</h5>
                              <h5 id="degreef1" class="mb-0 font-weight-bold" style="color: #1C2331; display: none;"> High 13°F - Low 13°F </h5>
                            
                            </div>

                            <div class="d-flex align-items-center">
                              <div class="flex-grow-1" style="font-size: 1rem;">
                                <div><i class="bi bi-wind" style="color: #868B94;"></i> <span class="ms-1"> 40 km/h </span></div>
                                <div><i class="bi bi-water" style="color: #868B94;"></i> <span class="ms-1"> 84% </span></div>
                                <!-- <div><i class="bi bi-sun" style="color: #868B94;"></i> <span class="ms-1"> 0.2h </span></div> -->
                              </div>
                              <div>
                                <img src="https://mdbcdn.b-cdn.net/img/Photos/new-templates/bootstrap-weather/ilu1.webp" width="100px">
                              </div>
                            </div>
                          </div>
                        </div>
                      </div>
                    </section>

                  </div>
                  <div  class="col-lg-3 bg-danger p-0">

                    <section class="h-auto">
                      <div class="">
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            <div class="d-flex">
                              <h6 class="flex-grow-1">12:00 am</h6>
                              <h6>6:00 am</h6>
                            </div>
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h2 class="mb-1">London</h2>
                              <h5 class="mb-4">2021-12-26</h5>
                              <h5 id="degreec1" class="mb-0 font-weight-bold" style="color: #1C2331;"> High 13°C - Low 13°C</h5>
                              <h5 id="degreef1" class="mb-0 font-weight-bold" style="color: #1C2331; display: none;"> High 13°F - Low 13°F </h5>
                            
                            </div>

                            <div class="d-flex align-items-center">
                              <div class="flex-grow-1" style="font-size: 1rem;">
                                <div><i class="bi bi-wind" style="color: #868B94;"></i> <span class="ms-1"> 40 km/h </span></div>
                                <div><i class="bi bi-water" style="color: #868B94;"></i> <span class="ms-1"> 84% </span></div>
                                <!-- <div><i class="bi bi-sun" style="color: #868B94;"></i> <span class="ms-1"> 0.2h </span></div> -->
                              </div>
                              <div>
                                <img src="https://mdbcdn.b-cdn.net/img/Photos/new-templates/bootstrap-weather/ilu1.webp" width="100px">
                              </div>
                            </div>
                          </div>
                        </div>
                      </div>
                    </section>

                  </div>
                  <div  class="col-lg-3 bg-danger p-0" >

                    <section class="h-auto">
                      <div class="">
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            <div class="d-flex">
                              <h6 class="flex-grow-1">12:00 am</h6>
                              <h6>6:00 am</h6>
                            </div>
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h2 class="mb-1">London</h2>
                              <h5 class="mb-4">2021-12-26</h5>
                              <h5 id="degreec1" class="mb-0 font-weight-bold" style="color: #1C2331;"> High 13°C - Low 13°C</h5>
                              <h5 id="degreef1" class="mb-0 font-weight-bold" style="color: #1C2331; display: none;"> High 13°F - Low 13°F </h5>
                            
                            </div>

                            <div class="d-flex align-items-center">
                              <div class="flex-grow-1" style="font-size: 1rem;">
                                <div><i class="bi bi-wind" style="color: #868B94;"></i> <span class="ms-1"> 40 km/h </span></div>
                                <div><i class="bi bi-water" style="color: #868B94;"></i> <span class="ms-1"> 84% </span></div>
                                <!-- <div><i class="bi bi-sun" style="color: #868B94;"></i> <span class="ms-1"> 0.2h </span></div> -->
                              </div>
                              <div>
                                <img src="https://mdbcdn.b-cdn.net/img/Photos/new-templates/bootstrap-weather/ilu1.webp" width="100px">
                              </div>
                            </div>
                          </div>
                        </div>
                      </div>
                    </section>

                  </div>
                  <div  class="col-lg-3 bg-danger p-0">

                    <section class="h-auto">
                      <div class="">
                        <div class="card" style="color: #4B515D;">
                          <div class="card-body">
                            <div class="d-flex">
                              <h6 class="flex-grow-1">12:00 am</h6>
                              <h6>6:00 am</h6>
                            </div>
                            <div class="d-flex flex-column text-center mt-5 mb-4">
                              <h2 class="mb-1">London</h2>
                              <h5 class="mb-4">2021-12-26</h5>
                              <h5 id="degreec1" class="mb-0 font-weight-bold" style="color: #1C2331;"> High 13°C - Low 13°C</h5>
                              <h5 id="degreef1" class="mb-0 font-weight-bold" style="color: #1C2331; display: none;"> High 13°F - Low 13°F </h5>
                            
                            </div>

                            <div class="d-flex align-items-center">
                              <div class="flex-grow-1" style="font-size: 1rem;">
                                <div><i class="bi bi-wind" style="color: #868B94;"></i> <span class="ms-1"> 40 km/h </span></div>
                                <div><i class="bi bi-water" style="color: #868B94;"></i> <span class="ms-1"> 84% </span></div>
                                <!-- <div><i class="bi bi-sun" style="color: #868B94;"></i> <span class="ms-1"> 0.2h </span></div> -->
                              </div>
                              <div>
                                <img src="https://mdbcdn.b-cdn.net/img/Photos/new-templates/bootstrap-weather/ilu1.webp" width="100px">
                              </div>
                            </div>
                          </div>
                        </div>
                      </div>
                    </section>

                  </div>
                </div>

              </div>
              
            </div>

            <div class="row p-3 mt-5 bg-secondary">

              <div class="col-lg-12 p-0">
                <p>Sort by</p>
              </div>

              <div class="col-lg-12">
                <div class="row">
                  <div class="col-lg-6">

                    <div class="row">
                      <div class="col-lg-12 p-0">
                        <p>5 flights found</p>
                      </div>
                      <div class="col-lg-12 bg-light p-3 mb-2">
                        
                      </div>
                      <div class="col-lg-12 bg-light p-3 mb-2">
                        
                      </div>
                      <div class="col-lg-12 bg-light p-3 mb-2">
                        
                      </div>
                      
                    </div>

                  </div>
                  <div class="col-lg-6 p-0">

                    <div class="row">
                      <div class="col-lg-6">

                        <div class="row">
                          <div class="col-lg-12">
                            <p>Economy</p>
                          </div>
                          <div class="col-lg-12 bg-light p-3 mb-2">
                            
                          </div>
                          <div class="col-lg-12 bg-light p-3 mb-2">
                            
                          </div>
                          <div class="col-lg-12 bg-light p-3 mb-2">
                            
                          </div>
                          
                        </div>

                      </div>
                      
                      <div class="col-lg-6">

                        <div class="row">
                          <div class="col-lg-12">
                            <p>Premium Economy</p>
                          </div>
                          <div class="col-lg-12 bg-light p-3 mb-2">
                            
                          </div>
                          <div class="col-lg-12 bg-light p-3 mb-2">
                            
                          </div>
                          <div class="col-lg-12 bg-light p-3 mb-2">
                            
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
      fetchedWeatherData: [],
      leftTemp1: '',
      leftTemp2: '',
      leftTemp3: '',
      leftTemp4: ''
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
      }

    },

    checkOut(val) {

      if(val !== null){
        let checkOutDate = val.toString()

        checkOutDate = checkOutDate.split(" ")
      
        this.dates.out = `${checkOutDate[2]} ${checkOutDate[1]} ${checkOutDate[3]}`;

        const months = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"];
        let monthIndex = months.indexOf(checkOutDate[1]);

        this.destinationDate = `${checkOutDate[3]}-${monthIndex+1}-${checkOutDate[2]}`

      }
      
    },

    fetchWeatherData(){
      axios.get(`https://api.weatherapi.com/v1/forecast.json?key=7361d83e5f7f4a219e6121225212812&q=${this.destinationCity}&dt=${this.destinationDate}`)
        .then(result => {

          // this.fetchedWeatherData = result.data
          // console.log(this.fetchedWeatherData)
          let weatherData = result.data
          console.log(weatherData)

          let sum1, sum2, sum3, sum4
          sum1 = sum2 = sum3 = sum4 = 0
          let temp_c_1, temp_c_2, temp_c_3, temp_c_4
          temp_c_1 = temp_c_2 = temp_c_3 = temp_c_4 = []

          for(let i=0;i<weatherData.forecast.forecastday[0].hour.length;i++){
            
            if(i>=0 && i<6){
              temp_c_1 = [...temp_c_1, weatherData.forecast.forecastday[0].hour[i].temp_c]

            }
            else if(i>=6 && i<12){
              temp_c_2 = [...temp_c_2, weatherData.forecast.forecastday[0].hour[i].temp_c]
            }
            else if(i>=12 && i<18){
              temp_c_3 = [...temp_c_3, weatherData.forecast.forecastday[0].hour[i].temp_c]
            }
            else if(i>=18 && i<24){
              temp_c_4 = [...temp_c_4, weatherData.forecast.forecastday[0].hour[i].temp_c]
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

          

          this.leftTemp1 = (sum1/6).toFixed(2)
          this.leftTemp2 = (sum2/6).toFixed(2)
          this.leftTemp3 = (sum3/6).toFixed(2)
          this.leftTemp4 = (sum4/6).toFixed(2)

          console.log(this.leftTemp1)
          console.log(this.leftTemp2)
          console.log(this.leftTemp3)
          console.log(this.leftTemp4)

      }).catch(err =>{
        console.log(err)
      })
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
