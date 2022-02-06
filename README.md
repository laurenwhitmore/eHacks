<!DOCTYPE html>
<html lang="en">
<head>
    <title>Page Title</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
<style>
body {
  font-family: Arial, Helvetica, sans-serif;
    }
.header{
  padding: 80px;
  text-align: center;
  background-color: pink;
  color: white;
}
.header h1{
  font-size: 35px;
  text-align: center;
  font-family: 'Courier New', Courier, monospace;
}
.time{
  font-size: 25px;
  font-family: 'Courier New', Courier, monospace;
}
.searchbar{
  padding: 14px;
}
*{
  box-sizing:border-box;
}
.row{
  display: flex;
  flex-wrap: wrap;
  
}
.tips{
  flex: 35%;
  background-color: rgb(250, 245, 245);
  padding: 20px;
  font-family: 'Courier New', Courier, monospace;
  text-align: center;
}
.upcoming{
  flex: 35%;
  background-color: rgb(247, 236, 236);
  padding: 20px;
}
.todo{
  flex:30%;
  background-color: rgb(250, 245, 245);
  padding: 20px;
}
.upcoming h2{
  font-family:'Courier New', Courier, monospace;
}
#img{
  position: relative;
}
.todo h2{
  font-family:'Courier New', Courier, monospace;
}

#newtask input{
    width: 75%;
    height: 45px;
    font-family: 'Poppins',sans-serif;
    font-size: 15px;
    border: 2px solid #d1d3d4;
    padding: 12px;
    color: #111111;
    font-weight: 500;
    position: relative;
    border-radius: 5px;
}
#newtask input:focus{
    outline: none;
    border-color: #f07ad6;
}

#newtask button{
    position: relative;
    float: right;
    width: 20%;
    height: 45px;
    border-radius: 5px;
    font-family: 'Poppins',sans-serif;
    font-weight: 500;
    font-size: 16px;
    background-color: #f359d9;
    border: none;
    color: #ffffff;
    cursor: pointer;
    outline: none;
}
#tasks{
    background-color: #ffffff;
    padding: 30px 20px;
    margin-top: 10px;
    border-radius: 10px;
    width: 100%;
    position: relative;
}
.task{
    background-color: #e6c5e1;
    height: 50px;
		margin-bottom: 8px;
    padding: 5px 10px;
    display: flex;
		border-radius: 5px;
    align-items: center;
    justify-content: space-between;
    border: 1px solid #939697;
    cursor: pointer;
}
.task span{
    font-family: 'Poppins',sans-serif;
    font-size: 15px;
    font-weight: 400;
}
.task button{
    background-color: #f167bc;
    color: #ffffff;
    height: 100%;
    width: 40px;
    border-radius: 5px;
    border: none;
    cursor: pointer;
    outline: none;
}

.completed{
    text-decoration: line-through;
}





@media screen and (max-width: 700px) {
  .row {
    flex-direction: column;
  }


}
</style>
</head>
<body onload=continuetime() >
<div class="header">
<h1>Good Morning Lauren</h1>
<p class="time">  
  <span  id="dateAndTime" >
  </span>
</p>
</div>
<div class="searchbar">
  <script async src="https://cse.google.com/cse.js?cx=438bef50d64b546ef">
  </script>
  <div class="gcse-search"></div>
</div>
<div class="row">
  <div class="tips">
      <img src="bulb-49007.png" height=50px >
      <h2>Quick tip of the day!</h2>
      <p>
        <span id="tipDisplay"></span>
      </p>
  </div>
  <div class="upcoming">
    <h2>Upcoming financial literacy events!</h2>
    <p></p>
    <p>
      <a href = "https://www.eventbrite.ca/d/canada--london/taxes/?lc=1&q=financial%20literacy&page=1">Tax Help for Canadians</a>
      <p></p>
      <a href = "https://www.eventbrite.ca/e/business-finance-basics-1-day-training-in-london-city-tickets-166146208783?aff=ebdssbdestsearch&keep_tld=1">Business Finance Basics Traning</a>
      <p></p>
      <a href = "https://bettermoneyhabits.bankofamerica.com/en/saving-budgeting/creating-a-budget">Creating a Budget</a>
      <p></p>
      <a href = "https://www.wealthsimple.com/en-ca/learn/how-to-save-for-a-house">How to Save for a House</a>


    </p>
  </div>
  <div class="todo">
    <h2>To do list</h2>
    <div class="container">
      <div id="newtask">
        <input type="text" placeholder="Task to be done..">
        <button id="push">Add</button>
     </div>
     <div id="tasks"></div>
     <script type="text/javascript">
      document.querySelector('#push').onclick = function(){
          if(document.querySelector('#newtask input').value.length == 0){
              alert("Please Enter a Task")
          }
          else{
              document.querySelector('#tasks').innerHTML += `
                  <div class="task">
                      <span id="taskname">
                          ${document.querySelector('#newtask input').value}
                      </span>
                      <button class="delete">
                          <i class="far fa-trash-alt"></i>
                      </button>
                  </div>
              `;
      
              var current_tasks = document.querySelectorAll(".delete");
              for(var i=0; i<current_tasks.length; i++){
                  current_tasks[i].onclick = function(){
                      this.parentNode.remove();
                  }
              }
          }
      }
          </script>
    </div>
  </div>
</div>
</body>
<script src="dateAndTime.js"></script>
<script src="tipGenerator.js"></script>
</html>
