# First-Game-on-JS
This is my First game with nambers on JS 
<meta charset="UTF-8">
<script type="text/javascript">
	
	
	function changePlayer(player){
		if(player==1){
			return 2;
		} else {
			return 1;
		}
	}


	function getValidNumber(player){
		while(true){
			var answer = prompt("Игрок " + player + " Введите число от 1 до 20. Нажмите q чтобы выйти ");
		if(!isValid(answer)){
			alert("Ну я же просил от 1 до 20");
		} else 
			return answer
		}
	}

	// Функция задает диапазон от 1 до 20
	function isValid(number){
		return number >= 1 && number <= 20 || number == "q" ;
	}
	// Функция проверяет близко ли располагаются числа или нет
	function almostEqual(number,answer){
		return number == answer + 1 || number == answer -1 ;
	}

	// Случайно целое число min max
	function getRandomInt(min,max)
{
	return Math.floor(Math.random() * (max - min + 1)) + min;
}
	// Задаем правильный ответ и количество попыток
	var answer = getRandomInt(1,20);	
	alert("Мы начинаем игру Угадайка. Вам нужно угадать число!");
	var player = 1;

	// Запускаем цикл который уменьшает количество попыток на 1
	do
	{
	var user_answer = getValidNumber(player);
	if (user_answer == "q"){
		alert("Game over! Right answer is " + answer); 
		break;	
	} else if(user_answer == answer){
		alert("Поздравляю вы выиграли! Правильный ответ " + answer);
		break;
	} else if(almostEqual(user_answer,answer)){
		alert("почти угадал! попробуй ещё");
	} else{
		alert("Вы не угадали! Попробуйте ещё ");
	}
	player = changePlayer(player);
	} while( true );

	


</script>
