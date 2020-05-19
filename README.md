# Snake Game
This project is made using HTML5 and JavaScript.

## HTML5
We create a canvas and set it height and width.<br>
<canvas id="snake" width="608" height="608">
</canvas>

## JavaScript
We select the canvas using document selector.

const cvs = document.getElementById("snake");<br>
const ctx = cvs.getContext("2d");<br>

The getContext gives alot of method and properties to draw anything on canvas.

### Load Images
let imageName = new Image();<br>
imageName.src = "path/img.png";<br>

### Load Audio
let audioName = new Audio();<br>
audioName.src = "path/audio.mp3";<br>
To play :- audioName.play();<br>

### Draw Images
ctx.drawImage(imageName,X,Y,Width,Height);

### Draw Rectangle
ctx.fillStyle="red";<br>
ctx.fillRect(X,Y,Width,Height);<br>
The single box of image is called unit.The box here is considered of 32px.

        i.Snake
          The snake is considered as array.
          let snake=[];
          //Starting Position
          snake[0]={ x : 9*box, y : 10*box};

          function draw(){
              ctx.drawImage(ground,0,0);
              for( let i = 0; i < snake.length ; i++){
                  ctx.fillStyle = ( i == 0 )? "green" : "white";
                  ctx.fillRect(snake[i].x,snake[i].y,box,box);

                  ctx.strokeStyle = "red";
                  ctx.strokeRect(snake[i].x,snake[i].y,box,box);
          }
       ii.Food
       The Food must be placed at random position everytime. So we use Math.Random function for it.So when the snake eat the food we donot pop or remove the tail we just add a new head.

### Control the Snake
The snake is controlled using the key . The key has keycode associated with it. The keyCode property in java script returns the key pressed and we can use that value to control our snake.

          #### Array.pop() && Array.unshift()
          Pop method removes the last element of array and unshift method add the new elment to the begining of array. So here we simply remove the tail and add a new head for the movement.


          // old head position
          let snakeX = snake[0].x;
          let snakeY = snake[0].y;

          // which direction
          if( d == "LEFT") snakeX -= box;
          if( d == "UP") snakeY -= box;
          if( d == "RIGHT") snakeX += box;
          if( d == "DOWN") snakeY += box;

          snake.pop();
          snake.unshift(newHead);

## Game Over
The game gets over when it hits itself or get crashed to the wall.
