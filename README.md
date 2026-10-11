<!DOCTYPE html>
<head>
    <meta charset="UTF-8">
    <title> 군대에서 만든 게임 </title>
    <style type = "text/css">
            canvas {border:1px solid black;}
    </style>
</head>
<body>
	<p> 야호~ </p>
	<canvas id="Canvas" width="800" height="608"></canvas>
	<p> 여기에서 꿀팁은, 이렇게 웹 브라우저와 메모장을 같이 켜놓고 메모장에서는 저장( Ctrl+S), 브라우저에서는 새로고침(F5) 누르면 빠르게 확인할 수 있습니다.</p>

	<script>

	let player_x=0;
	let key_a = 0;
	let key_d = 0;
	const FPS=60;
    const canvas = document.getElementById('Canvas');
    const ctx = canvas.getContext("2d");

	document.addEventListener('keydown', (event) => {
    	if(event.key=='a')
		{
		    key_a = 1;
		}
    	if(event.key=='d')
		{
			key_d = 1;
		}
	});
	document.addEventListener('keyup', (event) => {
    	if(event.key=='a')
		{
			key_a = 0;
		}
    	if(event.key=='d')
		{
			key_d = 0;
		}
	});

	function game()
	{
  		step();
		draw();
	}
	function step()
	{
		if(key_a==1)
			player_x-=4;
		if(key_d==1)
			player_x+=4;
	}
	function draw()
	{
        ctx.clearRect(0,0,canvas.width,canvas.height);
		ctx.fillRect(player_x,400,32,32);
	}
	setInterval(game,1000/FPS);

	</script>
</body>
</html>
