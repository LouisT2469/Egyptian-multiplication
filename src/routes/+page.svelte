<script lang="ts">
	let a1: number; //Variabeln definieren
	let b1: number;
	let sumb = 0;

	function AegyptenRechnen(a: any, b: any) {
		sumb = 0; //Variable sumb auf 0 setzen, damit bei mehrmaligem Rechnen nicht immer weiter addiert wird
		while (a >= 1) { //Inhalt wird solange aisgeführt, bis Variable a kleiner als 1 ist
			if (a % 2 === 1) {//Ist a ungerade?
				sumb += b;//b=b+sum
				a = Math.floor(a / 2); //Variable a durch 2 rechnen und auf eine ganze Zahl abrunden
				b = b * 2;
			} else { //wenn Variable a gerade ist
				a = Math.floor(a / 2);
				b = b * 2;
			}
		}
		{
			console.log(sumb); //Ergebnis in Konsole anzeigen
		}
	}
</script>

<div class="flex justify-center items-center flex-col mt-16 space-y-4">
	<div class="flex space-y-2 flex-col text-center">
		<span class="text-3xl font-bold">Multiplikation wie die Ägypter</span>
		<span>Louis Taube Klasse 10d</span>
	</div>

	<!--Formular mit Ausführung der Funktion (Variabeln a1 und b1 werden auf a und b übergeben)-->
	<form on:submit|preventDefault={() => AegyptenRechnen(a1, b1)}>
		<!--Eingabe des Input auf Variable a1 binden (mit bind: usw.)-->
		<input class="w-12 text-center outline-none" type="number" placeholder="a" bind:value={a1} />
		<span class="font-extrabold"> * </span>
		<!--Eingabe des Input auf Variable b1 binden (mit bind: usw.)-->
		<input class="w-12 text-center outline-none" type="number" placeholder="b" bind:value={b1} />
		<button class="hover:scale-125" title="rechnen">🚀</button>
	</form>

	<div class="flex flex-col space-y-2 text-center">
		<span class="font-extrabold">=</span>
		<!--Ergebnis anzeigen (durch Variable sumb)-->
		<span class="underline decoration-double">{sumb}</span>
	</div>
</div>
