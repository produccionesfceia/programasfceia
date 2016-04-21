# programasfceia
info2/infoaplicada/dejadehacerclic!

PRACTICA 0:

EJERCICIO 3:
#include <stdio.h>
 // ejercicio 3


int main(){
	int vector [5];
	int cant_lluvia;
	int i, j;
	int mayor_lluvia; //almacena la cantidad de lluvia
	int menor_lluvia; // almacena la cantidad de menor lluvia
	int marcador; //para saber el dia que llovio mas
	int menormarcador; //para saber que dia llovio menos

	for( i=0; i<5; i++){
		printf (" \n Ingrese el valor de lluvia: ");
		scanf (" %d", &cant_lluvia);
		vector[i] = cant_lluvia;
		//printf ("El valor de lluvia es: %d \n", cant_lluvia);
	}
	getchar();
	mayor_lluvia = vector[0];
	menor_lluvia = vector[0];

	for(i=0; i<5; i++)
		if (mayor_lluvia <= vector[i]){
			mayor_lluvia = vector [i];
			marcador = i;
		}
		else{
		mayor_lluvia = vector[0];
		marcador = i;
		}
	for (j=0; j<5; j++)
		if (vector[j] <= menor_lluvia){
			menor_lluvia = vector[j];
			menormarcador = j;
		}
		else {
			menor_lluvia = vector [0];
			marcador = j;
		}
		printf ("El dia que mas llovio fue %d \t y llovio: %d mm \n", marcador, mayor_lluvia);
		printf ("El dia que menos llovio fue %d \t y llovio: %d mm \n", menormarcador, menor_lluvia);
		//getchar();
		getchar();
		

}



EJERCICIO 4

#include <stdio.h>
void matriz( int vector[3][3]){
	int i, j;
	for (i=0; i<3; i++)
	{
	for (j=0; j<3; j++)
		{
		printf("\n Ingrese el valor de la fila y columna [%d] [%d]:", i , j);
		scanf(" %d", &vector [i][j]);
		}
	}
}

void matriza( int matriz_a[3][3]){
	int i, j;
	for (i=0; i<3; i++)
	{
	for (j=0; j<3; j++)
		{
		printf("\n Ingrese el valor de la fila y columna [%d] [%d]:", i , j);
		scanf(" %d", &matriz_a [i][j]);
		}
	}
}
void matrizb( int matriz_b[3][3]){
	int i, j;
	for (i=0; i<3; i++)
	{
	for (j=0; j<3; j++)
		{
		printf("\n Ingrese el valor de la fila y columna [%d] [%d]:", i , j);
		scanf(" %d", &matriz_b [i][j]);
		}
	}
}

int main()
{
int i,j, f, c, fil, col; //para ciclos for
int traza=0, cant, k;
int vector [3][3], matriz_a [3][3], matriz_b[3][3], producto[3][3]; //matrix 3*3
int transpuesta [3][3]; //matrix transpuesta 3*3
int aux=0;


/*matriz(vector); //llamada a subrutina para cargar matriz


printf("\n MATRIX ORDENADA \n");
for (i=0; i<3; i++) // ciclo for para imprimir en pantalla la matriz ordenada
	{
		for (j=0; j<3; j++)
		{
			printf(" %d", vector [i][j]);
		}
		printf(" \n");
	}


for (f=0; f<3; f++) //ciclo para calcular tranza
{
	for (c=0; c<3; c++)
	{
		if (c==f)
		{
			traza =  traza + (vector[f][c]);
		}
		else 
		{ 
		traza = traza;
		}
	}

}

for (fil=0; fil<3; fil++) // matriz transpuesta
	{
		for (col=0; col<3; col++)
		{
			if (col == fil)
			{
				transpuesta [fil][col] = vector [fil][col];
			}
			else 
			{
				transpuesta [fil][col] = vector [col][fil];
			}
		}
	}


printf("\n MATRIX TRANSPUESTA \n");
	for (fil=0; fil<3; fil++) // ciclo for para imprimir en pantalla matriz traspuesta 
	{
		for (col=0; col<3; col++)
		{
			printf(" %d", transpuesta [fil][col]);
		}
		printf(" \n");
	}
		

printf("\n El valor de la traza es: %d \n", traza);
getchar();
getchar();
*/
printf("\n Se cargaran las nuevas matrices para el producto \n");

matriza(matriz_a);
matrizb(matriz_b);
//producto[0][0]= 0,0;
printf("\n producto de matrices ... \n");
cant=0;
for (i=0; i<3; i++){
	for (j=0; j<3; j++){
		producto[i][j] = 0;
		for (k=0; k<3; k++){
		producto[i][j] = producto [i][j]+((matriz_a[i][k])*(matriz_b[k][j]));
	}
	}
printf(" %d", aux);

//producto[i][cant]=aux;
//cant=cant+1;
}
printf("\n MATRIX PRODUCTO \n");
for (i=0; i<3; i++) // ciclo for para imprimir en pantalla la matriz producto
	{
		for (j=0; j<3; j++)
		{
			printf(" %d", producto [i][j]);
		}
		printf(" \n");
	}
getchar();
getchar();
}


EJERCICIO 5

#include <stdio.h>

int main (){

char a =75;
char b=8;
char res;
printf(" a= %d b= %d", a,b);
res= a&b;
printf(" %d", res);
if (a&b)
printf("es un 1");
else printf("es un cero");
getch();
}

EJERCICIO 8
#include <stdio.h>

#define minimo2(a,b) ((a<b)? a:b)
#define minimo3 (c,  minimo2(a,b)) ((c<minimo2(a,b))? c : minimo2(a,b))
main(){
	int x, y, z,a,b,c, valormin, aux;
	printf(" Ingrese el primer numero: ");
		scanf(" %d", &x);
	printf(" Ingrese el segundo numero: ");
		scanf(" %d", &y);
	printf(" Ingrese el tercer numero: ");
		scanf(" %d", &z);
	//valormin = minimo2(x,y);
	aux= minimo3(z,minimo2(x,y));
	printf("el minimo es %d", aux);
	getchar();
		getchar();

}

#include <stdio.h>

int paridad_par (int a){
int i, cant=0;

for (i=0; i<8; i++){
	if ((a>>i) & 1)
		cant +=1;
	}
	if (cant%2==0) 
		return (a);
	else return (a | (1<<8));
}
main(){
	int a;
	printf("numero:");
	scanf(" %d", &a);
	printf("el numero devuelto es: %d", paridad_par(a));
	getch();

}

EJERCICIO 10
#include <stdio.h>

// se me pide que el numero x tenga en el bit menos significativo un 0 por eso eligo el numero B4

int unsigned rightRot(unsigned x, int n){
	int i;
	for (i=0; i<n;i++){
		if((x & 1) == 0) //el bit es un cero
			x = x>>1;
		else { // el bit es un uno
			x = x>>1;
			x= x | 0x80; // con el 0x80 lo que hago es hacer un or y poder asignar un 1 adelante del todo
		}
	}
	return x;
}


main(){
	unsigned x;
	int n;

	x=0xB4; //numero en hexadecimal que voy a rotar a derecha
	printf("Ingrese la cantidad de bits que desea rotar a derecha: ");
	scanf(" %d", &n);
	printf("El numero rotado a derecha es: %d", rightRot(x,n));
	getch();

}

EJERCICIO 11

#include <stdio.h>

int unsigned setBits(unsigned x, int p){
	int i, j, puntero = 7 + p;
	for (i=0;i<p;i++){
		x=x<<1; //muevo a izq todo 1 bit ...
			/*if((x<<(8+i))&1){ //pregunto si ahora encuento un 1
				x = 0<<(i+7);
				printf("hol");
			}*/
		printf(" %d \n", x);
		}
	for (j=7;j<puntero;j++){
		x =  (0<<j);
		printf("\n %d",x);
	}
			/*if ((x<<8)&1){
				x = (x ^ (1<<i+7));
				printf("punt\n");
	}*/
	
	return (x);
}


main(){
	unsigned x;
	int p, xp;
	x = 0xB4;
	printf("\n Ingrese la cantidad de bits que deseaa desplazar a izq: ");
	scanf(" %d", &p);
	while (p > 7){
		printf("\n Ingrese una cantidad de bits mayor o igual que 7");
		printf("\n Vuelva a ingresar los bits a desplazar: ");
		scanf(" %d", &p);
	}
	printf("\n El numero desplazado a izq es: %d", setBits(x,p));
	getch();
}




