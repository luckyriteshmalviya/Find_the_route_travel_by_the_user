# Find_the_route_travel_by_the_user
Find the route travel by the user across the given list of cities by their tickets.  
  
   
  
### Question :-  
 Your son took a vacation through Europe without telling you. When the kid returned from the vacation you asked him where did he go. The kid told you: Dad I went to these cities:   
 Amsterdam, Kiev, Zurich, Prague, Berlin, Barcelona.  
  
 I used only train as transportation and these were the available tickets:  
 Paris-Skopje, Zurich-Amsterdam, Prague-Zurich, Barcelona-Berlin, Kiev-Prague, Skopje-Paris, Amsterdam-Barcelona, Berlin-Kiev, Berlin-Amsterdam.  
  
 You know that your kid started with Kiev  
  
 Write a data structure and algorithm that will give you the route which your son was traveling.  
   
     
### Solution :-   

The Data Structure should be like this -   
    
 let tickets = {  
  Paris: "Paris-Skopje",    
  Zurich: "Zurich-Amsterdam",  
  Prague: "Prague-Zurich",  
  Barcelona: "Barcelona-Berlin",  
  Kiev: "Kiev-Prague",  
  Skopje: "Skopje-Paris",  
  Amsterdam: "Amsterdam-Barcelona",  
  Berlin: "Berlin-Amsterdam",  
  Berlin: "Berlin-Kiev",  
};  
  
let cities = ["Amsterdam", "Kiev", "Zurich", "Prague", "Berlin", "Barcelona"];  
let currentStop = "Kiev";  
let route = [];  
  
 function findRoute(tickets, cities, currentStop, route) {  
  if (tickets.hasOwnProperty(currentStop)) {  
    route.push(tickets[currentStop]);  
    let index = cities.indexOf(currentStop);  
    cities.splice(index, 1);  
    let newStop = route[route.length - 1].split("-");  
    currentStop = newStop[1];  
  }  
  if (cities.length < 1) {  
    return route;  
  } else {  
    return findRoute(tickets, cities, currentStop, route);  
  }  
}  

console.log(findRoute(tickets, cities, currentStop, route));  


  
## Answer :- 
  
[  
  'Kiev-Prague',          
  'Prague-Zurich',        
  'Zurich-Amsterdam',     
  'Amsterdam-Barcelona',  
  'Barcelona-Berlin',     
  'Berlin-Kiev'  
]  

