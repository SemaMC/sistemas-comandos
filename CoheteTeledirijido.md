**Este sistema de comandos tiene como funcionalidad hacer que los cohetes lanzados por el jugador se dirijan al enemigo mas cercano:**

<br>Primero que todo debemos de crear los siguientes objetivos de scoreboard:<br>
1. `id`<br>
2. `idR`<br><br>

Despues de crear estos dos objetivos, debemos de ejecutar el siguiente comando en el chat: <br>
`/scoreboard players set idC id 1`<br><br>

<br>**Estos son los comandos de la primera torre:**<br>
<br>1. `execute as @a run execute unless score @s id matches 1.. run scoreboard players operation @s id = idC id`<br>
> Repetir<br>
> Siempre Activo<br>
> Tiene que mirar hacia arriba

<br>2. `scoreboard players add idC id 1`<br>
> Cadena<br>
> Siempre Activo<br>
> Tiene que mirar hacia arriba<br>

<br>**Estos son los comandos de la segunda torre:**<br>
<br>1. `execute as @a[hasitem={item=crossbow,location=slot.weapon.mainhand}] at @s anchored eyes as @e[type=fireworks_rocket,r=0.4] at @s run execute unless score @s idR matches 1.. run scoreboard players operation @s idR = @e[c=1,scores={id=-1..}] id`<br>
> Repetir<br>
> Siempre Activo<br>
> Tiene que mirar hacia arriba<br>

<br>3. `execute as @e[type=fireworks_rocket,scores={idR=1..}] at @s run execute as @e[c=1,r=10,rm=0.1,type=chicken] unless score @s id = @e[c=1] idR facing entity @s eyes run tp @e[c=1] ^^^0.6`<br>
> Cadena<br>
> Siempre Activo<br>
> Tiene que mirar hacia arriba<br>

<br>4. `execute as @e[type=fireworks_rocket] at @s run execute unless score @s idR matches -1.. unless entity @e[r=1,rm=0.1] run scoreboard players set @s idR -2`<br>
> Cadena<br>
> Siempre Activo<br>
> Tiene que mirar hacia arriba<br>

<br>5. `scoreboard players set @e[family=mob] id -1`<br>
> Cadena<br>
> Siempre Activo<br>
> Tiene que mirar hacia arriba<br>

<br>**Nota:**
*Debajo de cada comando encuentras la configuracion del bloque de comandos.*

<br>**Listo, estos son todos los comandos, el sistema deberia de funcionar bien, si tienes algun problema u error, puedes realizar lo siguiente:**
1. Abrir un "issue" aqui en GitHub<br>
2. Hablarme por discord: `@SemaMC`<br>
3. Poner un comentario en el video de YouTube<br>
