<!DOCTYPE html>
<html>
<head>
	<title>Mensaje para Ximena</title>
	<style>
		body {
			background-color: #f0f0f0;
			font-family: Arial, sans-serif;
			color: #333;
			text-align: center;
		}
		.contenido {
			display: none;
		}
		.mostrar {
			display: block;
		}
	</style>
</head>
<body>
	<h2 id="mensaje-inicial"><b>Circe puedes volver a abrir este enlace en:</b></h2>
	<div id="cuenta-regresiva"></div>
	<div class="contenido" id="mensaje"> 
  <p>Mmm pues quisiera empezar agradeciendo que fuiste un gran pilar para mi en los momentos más difíciles de mi vida y siempre me ayudaste en salir a flote aprecio demasiado cada una de tus palabras porque me sirvieron demasiado para no tomar decisiones estupidas en momentos tan fuertes de mi vida gracias por ser mi mejor amiga circe gracias por apoyarme sin esperar nada a cambio contigo aprendí que no todas las personas de este planeta me quieren hacer daño o quieren buscar algo de mi te agradezco porque gracias ati mejore muchisimo como persona y aprendí demasiadas cosas solo me queda decirte gracias y felicidades por tu fiesta siento tanto que no pueda asistir después de tanto esperar solo me queda decirte que tome la decisión de crecer mas como persona y tengo bastantes razones para hacer lo que hice lo siento por eso pero estaba en un mal momento si es que llegas a perdonarme me gustaría tener la oportunidad de volver a verte algun día mmm si me estoy despidiendo pero quisiera verte el dia q cumpla mi sueño si es que vuelves a saber de mi espero que sea porque lo viste en la tele o internet solo me queda decirte muchísimas gracias por todo y decirte que esto no es un adios es un hasta pronto</p></div>
	<div id="gracias" style="display: none;">
		<h1>GRACIAS</h1>
	</div>
	<script>
		var fechaActual = new Date();
		var fechaMostrar = new Date('2024-08-03T10:00:00');
		var fechaOcultar = new Date('2024-08-05T17:00:00');
		var diferencia = fechaMostrar - fechaActual;
		var dias = Math.floor(diferencia / (1000 * 60 * 60 * 24));
		var horas = Math.floor((diferencia % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
		var minutos = Math.floor((diferencia % (1000 * 60 * 60)) / (1000 * 60));
		var segundos = Math.floor((diferencia % (1000 * 60)) / 1000);
		document.getElementById('cuenta-regresiva').innerHTML = 'La página se abrirá en ' + dias + ' días, ' + horas + ' horas, ' + minutos + ' minutos y ' + segundos + ' segundos';
		var intervalo = setInterval(function() {
			diferencia -= 1000;
			dias = Math.floor(diferencia / (1000 * 60 * 60 * 24));
			horas = Math.floor((diferencia % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
			minutos = Math.floor((diferencia % (1000 * 60 * 60)) / (1000 * 60));
			segundos = Math.floor((diferencia % (1000 * 60)) / 1000);
			document.getElementById('cuenta-regresiva').innerHTML = 'La página se abrirá en ' + dias + ' días, ' + horas + ' horas, ' + minutos + ' minutos y ' + segundos + ' segundos';
			if (diferencia <= 0) {
				clearInterval(intervalo);
				document.getElementById('mensaje-inicial').style.display = 'none';
				document.getElementById('mensaje').classList.add('mostrar');
				document.getElementById('cuenta-regresiva').style.display = 'none';
				var intervaloOcultar = setInterval(function() {
					var diferenciaOcultar = fechaOcultar - new Date();
					if (diferenciaOcultar <= 0) {
						clearInterval(intervaloOcultar);
						document.getElementById('mensaje').style.display = 'none';
						document.getElementById('gracias').style.display = 'block';
					}
				}, 1000);
			}
		}, 1000);
	</script>
</body>
</html>
