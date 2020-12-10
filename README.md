# Event2-mdn-learning
using canvas to create circle and moving it 
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Event2-skill-test-moveing circle with keyboard</title> 
    <style>
        canvas {
            background-color: pink;
        }
    </style>   
  </head>
  <body>
    <canvas width="400" height="400"></canvas>

    <script>
      const canvas = document.querySelector('canvas');
      var x = 200;
      var y = 200;
      var i = 10;

      function drawCircle(x, y, radius){
        if(canvas.getContext){
          let ctx = canvas.getContext('2d');
          
          ctx.clearRect(0,0,canvas.width,canvas.height);
          ctx.beginPath();
          ctx.arc(x, y, radius, 0, 2 * Math.PI);
          ctx.fill();
          }
        }

      function moveUp(){
        if(y>=0){
          y = y - i;  
        }
        drawCircle(x,y,30);   
        }

      function moveDown(){
        if(y<=400){
          y = y + i; 
        }
        drawCircle(x,y,30); 
        }

      function moveRight(){
        if(x<= 400){
          x = x + i;  
        }  
        drawCircle(x,y,30);
        }
   
      function moveLeft(){
        if(x>=0){
          x = x - i;  
        }
        drawCircle(x,y,30);
        }

       window.addEventListener('keydown',function(e){
         switch(e.code){
           case 'KeyW':
             moveUp();
             break;
           case 'KeyS':
             moveDown();
             break;
           case 'KeyA':
             moveLeft();
             break;
           case'KeyD':
             moveRight();
             break;      
            }    
         });

 
    </script>
  </body>    
</html>
