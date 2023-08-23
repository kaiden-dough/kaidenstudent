# Tic Tac Toe
<style>
    .canvas-container{
        position: relative;
        width: 660px;
        height: 660px;
    }
    #canvas {
        position: absolute;
        background-color:lightgrey
    }
    #button1 {
        font-size:100px;
        background-color:#F6F6F6;
        border:none;
        position:absolute;
        left:7.4%;
        top:13.3%;
        width: 195px;
        height: 195px;
    }
    #button2 {
        font-size:100px;
        background-color:#F6F6F6;
        border:none;
        position:absolute;
        left:34.5%;
        top:13.3%;
        width: 195px;
        height: 195px;
    }
    #button3 {
        font-size:100px;
        background-color:#F6F6F6;
        border:none;
        position:absolute;
        left:61.6%;
        top:13.3%;
        width: 195px;
        height: 195px;
    }
    #button4 {
        font-size:100px;
        background-color:#F6F6F6;
        border:none;
        position:absolute;
        left:7.4%;
        top:40%;
        width: 195px;
        height: 195px;
    }
    #button5 {
        font-size:100px;
        background-color:#F6F6F6;
        border:none;
        position:absolute;
        left:34.5%;
        top:40%;
        width: 195px;
        height: 195px;
    }
    #button6 {
        font-size:100px;
        background-color:#F6F6F6;
        border:none;
        position:absolute;
        left:61.6%;
        top:40%;
        width: 195px;
        height: 195px;
    }
    #button7 {
        font-size:100px;
        background-color:#F6F6F6;
        border:none;
        position:absolute;
        left:7.4%;
        top:66.7%;
        width: 195px;
        height: 195px;
    }
    #button8 {
        font-size:100px;
        background-color:#F6F6F6;
        border:none;
        position:absolute;
        left:34.5%;
        top:66.7%;
        width: 195px;
        height: 195px;
    }
    #button9 {
        font-size:100px;
        background-color:#F6F6F6;
        border:none;
        position:absolute;
        left:61.6%;
        top:66.7%;
        width: 195px;
        height: 195px;
    }
</style>
<html>
<div class = "class-container">
    <type id="whowin"></type>
    <canvas class="canvas" id="Board" width="660" height="660" style="border:3px solid #000000;"></canvas>
    <button id='button1' onclick="oneaction()"></button> 
    <button id='button2' onclick="twoaction()"></button> 
    <button id='button3' onclick="threeaction()"></button> 
    <button id='button4' onclick="fouraction()"></button> 
    <button id='button5' onclick="fiveaction()"></button> 
    <button id='button6' onclick="sixaction()"></button> 
    <button id='button7' onclick="sevenaction()"></button> 
    <button id='button8' onclick="eightaction()"></button> 
    <button id='button9' onclick="nineaction()"></button> 
</div>
</html>
<script>
    var turn = 0
    var one = 0
    var two = 0
    var three = 0
    var four = 0
    var five = 0
    var six = 0
    var seven = 0
    var eight = 0
    var nine = 0
    var win = false
    var winner = ""
    const xo = ["X","O"]
    var b = document.getElementById("Board");
    var board = b.getContext("2d");
    board.lineWidth = 3;
    function reset(){
        turn = 0
        one = 0
        two = 0
        three = 0
        four = 0
        five = 0
        six = 0
        seven = 0
        eight = 0
        nine = 0
        win = false
        winner = ""
        board.clearRect(0, 0, b.width, b.height)
        document.getElementById("button1").innerHTML = ""
        document.getElementById("button2").innerHTML = ""
        document.getElementById("button3").innerHTML = ""
        document.getElementById("button4").innerHTML = ""
        document.getElementById("button5").innerHTML = ""
        document.getElementById("button6").innerHTML = ""
        document.getElementById("button7").innerHTML = ""
        document.getElementById("button8").innerHTML = ""
        document.getElementById("button9").innerHTML = ""
        document.getElementById("whowin").innerHTML = ""
        drawBoard()
    }
    function won(){
        if(win){
            alert(winner + " wins")
            reset()
        }
    }
    function testwin(){
        if(one == two && two == three && one != 0 && two!=0 && three!=0){
            console.log(one,"wins")
            win = true
            winner = one
            won()
        }
        else if(four == five && five == six && four != 0 && five!=0 && six!=0){
            console.log(four,"wins")
            win = true
            winner = four
            won()
        }
        else if(seven == eight && eight == nine && seven != 0 && eight!=0 && nine!=0){
            console.log(seven,"wins")
            win = true
            winner = seven
            won()
        }
        else if(one == five && five == nine && one != 0 && five!=0 && nine!=0){
            console.log(one,"wins")
            win = true
            winner = one
            won()
        }
        else if(three == five && five == seven && three != 0 && five!=0 && seven!=0){
            console.log(three,"wins")
            win = true
            winner = three
            won()
        }
        else if(one == four && four == seven && one != 0 && four!=0 && seven!=0){
            console.log(one,"wins")
            win = true
            winner = one
            won()
        }
        else if(two == five && five == eight && two != 0 && five!=0 && eight!=0){
            console.log(two,"wins")
            win = true
            winner = two
            won()
        }
        else if(three == six && six == nine && three != 0 && six!=0 && nine!=0){
            console.log(three,"wins")
            win = true
            winner = three
            won()
        }
        else{
            console.log("no")
            win = false
        }
    }
    function oneaction(){
        if (one==0){
            document.getElementById("button1").innerHTML = xo[turn]
            one=xo[turn]
            console.log(one)
            if (turn == 1){
                turn=0
            }
            else{
                turn=1
            }
            console.log("huh")
            testwin()
        }
        else{
            alert("Try Again")
        }
    }
    function twoaction(){
        if (two==0){
            document.getElementById("button2").innerHTML = xo[turn]
            two=xo[turn]
            console.log(two)
            if (turn == 1){
                turn=0
            }
            else{
                turn=1
            }
            testwin()
        }
        else{
            alert("Try Again")
        }
    }
    function threeaction(){
        if (three==0){
            document.getElementById("button3").innerHTML = xo[turn]
            three=xo[turn]
            console.log(three)
            if (turn == 1){
                turn=0
            }
            else{
                turn=1
            }
            testwin()
        }
        else{
            alert("Try Again")
        }
    }
    function fouraction(){
        if (four==0){
            document.getElementById("button4").innerHTML = xo[turn]
            four=xo[turn]
            console.log(four)
            if (turn == 1){
                turn=0
            }
            else{
                turn=1
            }
            testwin()
        }
        else{
            alert("Try Again")
        }
    }
    function fiveaction(){
        if (five==0){
            document.getElementById("button5").innerHTML = xo[turn]
            five=xo[turn]
            console.log(five)
            if (turn == 1){
                turn=0
            }
            else{
                turn=1
            }
            testwin()
        }
        else{
            alert("Try Again")
        }
    }
    function sixaction(){
        if (six==0){
            document.getElementById("button6").innerHTML = xo[turn]
            six=xo[turn]
            console.log(six)
            if (turn == 1){
                turn=0
            }
            else{
                turn=1
            }
            testwin()
        }
        else{
            alert("Try Again")
        }
    }
    function sevenaction(){
        if (seven==0){
            document.getElementById("button7").innerHTML = xo[turn]
            seven=xo[turn]
            console.log(seven)
            if (turn == 1){
                turn=0
            }
            else{
                turn=1
            }
            testwin()
        }
        else{
            alert("Try Again")
        }
    }
    function eightaction(){
        if (eight==0){
            document.getElementById("button8").innerHTML = xo[turn]
            eight=xo[turn]
            console.log(eight)
            if (turn == 1){
                turn=0
            }
            else{
                turn=1
            }
            testwin()
        }
        else{
            alert("Try Again")
        }
    }
    function nineaction(){
        if (nine==0){
            document.getElementById("button9").innerHTML = xo[turn]
            nine=xo[turn]
            console.log(nine)
            if (turn == 1){
                turn=0
            }
            else{
                turn=1
            }
            testwin()
        }
        else{
            alert("Try Again")
        }
    }
    function drawBoard(){
        board.clearRect(0, 0, b.width, b.height)
        board.beginPath();
        board.moveTo(230, 30);
        board.lineTo(230, 630);
        board.moveTo(430, 30);
        board.lineTo(430, 630);
        board.moveTo(30, 230);
        board.lineTo(630, 230);
        board.moveTo(30, 430);
        board.lineTo(630, 430);
        board.closePath();
        board.stroke();
    }
    drawBoard()
</script>