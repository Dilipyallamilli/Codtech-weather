<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Weather App</title>
    <link rel="stylesheet" href="styles.css">
    <link href="https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css" rel="stylesheet">
  </head>
  <body>
    <div class="container">
        <div class="search-box">
            <i class='bx bxs-map'></i>
            <input id = "search-btn" type="text" placeholder="Enter Your Location">
            <button class="bx bx-search"></button>
        </div>
        <div class="weather-box">
            <div class="box">
                <div class="info-weather">
                    <div class="weather">
                        <img src="images/rain.png"></img>
                        <p class="temperature"> 0 <span>°C</span></p>
                        <p class="description">Broken clouds</p>
                    </div>

                </div>
            </div>
        </div>

        <div class="weather-details">
            <div class="humidity">
                <i class="bx bx-water"></i>
                <div class="text">
                    <div class="info-humidity">
                        <span>0%</span>
                    </div>
                    <p>Humidity</p>
                </div>
            </div>
            <div class="wind">
                <i class="bx bx-wind"></i>
                <div class="text">
                    <div class="info-wind">
                        <span>0Km/h</span>
                    </div>
                    <p>Wind Speed</p>
                </div>
            </div>
            
        </div>
        <div class="not-found">
            <div class="box">
                <img src="images/404-error.png">
                <p> Location not found !!</p>
            </div>
        </div>
    </div>
    <script src="script.js"></script>
  </body>
</html>



********************Style.css********************
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&display=swap");

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Poppins",sans-serif;
}

body{
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background: url('images/198562-landscapes-landscape-nature-sky-storm-outdoors-weather-cloudy.jpg');
    background-size: cover;
    background-position: center;
}

.container{
    position: relative;
    width: 400px;
    height: 100px;
    background: rgb(245,245,245,0.1);
    backdrop-filter: blur(30px);
    border: 2px solid rgba(255,255,255,.2);
    border-radius: 16px;
    padding: 20px;
    color: #fff;
    transition: height .6s ease;
}

.search-box{
    position: relative;
    width: 100%;
    height: 55px;
    display: flex;
    align-items: center;
}
.search-box i{
    position: absolute;
    left: 10px;
    border-radius: 10px;;
    font-size: 20px;
}

.search-box input{
    position: absolute;
    width: 100%;
    height: 100%;
    background: transparent;
    border: 2px solid rgba(255,255,255,.2);
    outline: none ;
    border-radius: 10px;
    font-size: 22px;
    color: #fff;
    font-weight: 500;
    text-transform: uppercase;
    padding: 0 48px 0 42px;

}

.search-box input{
    color: #fff;
    text-transform: capitalize;
}

.search-box button{
    position: absolute;
    right: 0;
    width: 40px;
    height: 100%;
    background: transparent;
    border: none;
    outline: none;
    font-size: 20px;
    color: #fff;
    padding: 0 40px 0 5px;
    cursor: pointer;
}
.weather-box{
    text-align: center;
    margin: 10px 0;
}

.weather-box,
.weather-details,
.not-found{
    overflow: hidden;
    visibility: hidden;
}

.weather-box.active,
.weather-details.active,
.not-found.active{
    visibility: visible;
}

.weather-box .box,
.not-found .box{
    transform: translateY(-100%);
}
.weather-box.active .box,
.not-found.active .box{
    transform: translateY(0%);
    transition: transform 1s ease;
    transition-delay: .6s;
}

.weather-box img{
    width: 60%;
}
.weather-box .temperature{
    position: relative;
    font-size: 64px;
    line-height: 1;
    font-weight: 700;
    margin: 20px 0 6px -30px;
}
.weather-box .temperature span{
    position: absolute;
    font-size: 24px;
    margin-left: 4px;
}

.weather-box .description{
    position: relative;
    font-size: 22px;
    font-weight: 500;
}

.weather-details{
    position: absolute;
    bottom: 40px;
    left: 0;
    width: 100%;
    padding: 0 20px;
    display: flex;
}

.weather-details .humidity,
.weather-details .wind{
    display: flex;
    align-items: center;
    width: 50%;
    transform: translateY(-100%);
}
.weather-details.active .humidity,
.weather-details.active .wind{
    transform: translateY(0%);
    transition: transform 1s ease;
    transition-delay: 1.0s;
}

.weather-details i{
    font-size: 56px;
    margin-right: 10px;
}
.weather-details .humidity{
    padding-left: 20px;
    justify-content: flex-start;
}

.weather-details .wind{
    padding-right: 20px;
    justify-content: flex-end;
}

.weather-details span{
    display: inline-block;
    font-size: 22px;
    font-weight: 500;
}

.weather-details p{
    font-size: 14px;
    font-weight: 500;
}
.not-found{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    text-align: center;
    margin-top: 110px;
}
.not-found img{
    width:  65%;
}
.not-found p{
    font-size: 22px;
    font-weight: 200;
    margin-top: 12px;
}


******************************script.js******************************

const container = document.querySelector('.container');
const search = document.querySelector('.search-box button');
const weatherBox = document.querySelector('.weather-box');
const weatherDetails = document.querySelector('.weather-details');
const error404 = document.querySelector('.not-found');

search.addEventListener('click',() =>{
    
    const APIKey = '6063be96ce55ff4c512e2897f7c2fc6b';
    
    const city = document.getElementById('search-btn').value;
    if(city==''){
        return ;
    }

    fetch(`https://api.openweathermap.org/data/2.5/weather?q=${city}&units=metric&appid=${APIKey}`).then(response => response.json()).then(json => {
    
    if(json.cod == '404'){
        container.style.height = '450px';
        weatherBox.classList.remove('active');
        weatherDetails.classList.remove('active');
        error404.classList.add('active');
        return;
    }

    container.style.height = '560px';
    weatherBox.classList.add('active');
    weatherDetails.classList.add('active');
    error404.classList.remove('active');

    const image = document.querySelector('.weather-box img');
    const temperature = document.querySelector('.weather-box .temperature');
    const description = document.querySelector('.weather-box .description');
    const humidity = document.querySelector('.weather-details .humidity span');
    const wind = document.querySelector('.weather-details .wind span');

        switch(json.weather[0].main){
            case 'Clear':
                image.src = 'images/sun.png';
                break;
            case 'Rain':
                image.src = 'images/rain.png';
                break;
            case 'Snow':
                image.src = 'images/snow.png';
                break;
            case 'Clouds':
                image.src = 'images/clouds.png';
                break; 
            case 'Mist':
                image.src = 'images/sun-clouds.png';
                break;                  
            case 'Haze':
                image.src = 'images/clouds.png';
                break;     
            default:
                image.src = 'images/sun.png';
        }
        temperature.innerHTML = `${parseInt(json.main.temp)}<span>°C</span>`;
        description.innerHTML = `${json.weather[0].description}`;
        humidity.innerHTML = `${json.main.humidity}%`;
        wind.innerHTML = `${parseInt(json.wind.speed)}Km/h`;
    });

});
