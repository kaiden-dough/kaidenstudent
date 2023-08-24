---
layout: default
title: Student Blog
---

## Kaiden Do's Page

Go to my [Github account](https://github.com/kaiden-dough) !!
![](https://cdn.discordapp.com/attachments/721225369872629760/1142726766381760584/IMG_1528.png)
## My Classes
1. AP Stats
2. Honors Principles of Engineering
3. AP CS A
4. AP Gov



<html>
<details open>
<summary>
Board
</summary>
<body>
    <button onclick="reset()">Clear</button>
    <br>
    <button onclick="minus()">-</button>
    <type id="dsize">3</type>
    <button onclick="add()">+</button>
    <canvas id="Board" width="700" height="700" style="border:3px solid #548BC2;" onmousemove="coordinate(event)" onmousedown="mousedown()" onmouseup="mouseup()"></canvas>
</body>
</details>
</html>
<script>
    var b = document.getElementById("Board");
    var board = b.getContext("2d");
    var down
    var size = 3
    function reset(){
        board.clearRect(0, 0, b.width, b.height)
    }
    function mousedown(){
        down = 1
    }
    function mouseup(){
        down = 0
    }
    function minus(){
        if (size>1){
            size--
        }
        document.getElementById("dsize").innerHTML = size
    }
    function add(){
        size++
        document.getElementById("dsize").innerHTML = size
    }
    function coordinate(event){
        console.log("hig")
        let rect = Board.getBoundingClientRect();
        var x=event.clientX - rect.left;
        var y=event.clientY - rect.top;
        console.log(x,"-",y)
        if(down){
            console.log("jit")
            board.fillStyle = "#548BC2"
            board.fillRect(x,y,size,size)
        }
}
</script>


# [TIC TAC TOE]({{site.baseurl}}/tictactoe)
# [I LOVE MY TOOLS]({{site.baseurl}}/2023/08/22/ILOVEMYTOOLS.html)