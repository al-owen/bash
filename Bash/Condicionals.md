Els condicionals a Bash permeten prendre decisions en els scripts basant-se en si una condició és certa (`true`) o falsa (`false`). Bash suporta diverses estructures condicionals, incloent `if`, `else`, `elif` (que és una abreviatura de "else if"), i `case`. Aquests condicionals poden provar per diverses condicions, incloent la comparació de valors, la comprovació de l'existència d'arxius, i els valors de sortida dels comandaments.

### Estructura `if`

La sintaxi bàsica de l'estructura `if` és la següent:

``` bash
if [ condició ]; then   
# Comandaments a executar si la condició és certa 
fi
```
### Afegint `else` i `elif`

Per afegir més branques al condicional, pots utilitzar `else` i `elif`:

``` bash

if [ condició ]; then     
	# Comandaments a executar si la condició és certa 
elif [ altra_condició ]; then     
	# Comandaments a executar si la segona condició és certa 
else
	#Comandaments a executar si cap de les condicions anteriors és certa 
fi
```
### Exemple

``` bash
numero=10 
if [ $numero -eq 10 ]; then
	echo "El número és 10." 
elif [ $numero -lt 10 ]; then
	echo "El número és menor que 10." 
else
	echo "El número és major que 10." 
fi
```
### Operadors de Comparació

Els condicionals sovint fan servir operadors de comparació dins dels corxets `[ ]` per avaluar condicions. Alguns dels operadors més comuns inclouen:

- `-eq`: igual a
- `-ne`: no igual a
- `-gt`: major que
- `-ge`: major o igual a
- `-lt`: menor que
- `-le`: menor o igual a
- `-z`: cadena buida
- `-n`: cadena no buida
- = : igual (per a cadenes)
- `!=`: no igual (per a cadenes)
- `-f`: l'arxiu existeix i és un fitxer regular
- `-d`: l'arxiu existeix i és un directori

### Estructura `case`

La instrucció `case` permet una gestió més neta i fàcil de llegir de múltiples condicions basades en el valor d'una variable:

```bash
case $variable in
	patró1)
		# Comandaments per a patró1         
	;;
	patró2)
		# Comandaments per a patró2
	;;
	*)
	# Comandaments per a qualsevol altre cas
	;; 
esac
```
### Exemple de `case`

``` bash
opcio="a"
case $opcio in
	a)
		echo "Has seleccionat l'opció A."
	;;
	b)
		echo "Has seleccionat l'opció B."
	;;
	*)
		echo "Opció desconeguda."
	;; 
esac
```
Els condicionals són fonamentals per a la lògica de decisió en els scripts de Bash, permetent executar diferents seccions de codi basades en condicions específiques. La correcta utilització d'aquestes estructures pot fer que els teus scripts siguin molt més potents i flexibles.