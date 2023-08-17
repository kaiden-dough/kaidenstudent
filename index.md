---
layout: default
title: Student Blog
---

## Kaiden Do's Page

Go to my [Github account](https://github.com/kaiden-dough) !!

## Board

<html>
<body>
    <canvas id="Board" width="700" height="700" style="border:3px solid #FFFFFF;" onmousemove="coordinate(event)" onmousedown="mousedown()" onmouseup="mouseup()"></canvas>
</body>
</html>
<script>
     var b = document.getElementById("Board");
    var board = b.getContext("2d");
    var down
    function mousedown(){
        down = 1
    }
    function mouseup(){
        down = 0
    }
    function coordinate(event){
        console.log("hig")
        let rect = Board.getBoundingClientRect();
        var x=event.clientX - rect.left;
        var y=event.clientY - rect.top;
        console.log(x,"-",y)
        if(down){
            console.log("jit")
            board.fillStyle = "#FFFFFF"
            board.fillRect(x,y,3,3)
        }
}
</script>
