

#include <stdio.h> 
#include <stdlib.h> 
#include <string.h> 
 
char *ChargerChaine(int N) { 
    char *chaine = (char *)malloc(N+1);  
    printf("Entrez une chaine de %d caracteres: ", N); 
    scanf("%d",N); 
    fgets(chaine, N+1, stdin); 
    chaine[strcspn(chaine, "\n")] = 0;  
    return chaine; 
} 
 
int Longueur(char *ch) { 
    int i = 0; 
    while (ch[i] != '\0') { 
        i++; 
    } 
    return i; 
} 
 
void ChargerTab(char *P, char Tab[]) { 
    strcpy(Tab, P); 
} 
 
void InverserTab(char Tab[], char T[], int m) { 
    for (int i = 0; i < m; i++) { 
        T[i] = Tab[m-i-1]; 
    } 
   T[m] = '\0';
} 
 
void AfficherTab(char Tab[], int m) { 
    for (int i = 0; i < m; i++) { 
        printf("%c", Tab[i]); 
    } 
    printf("\n"); 
} 
 
int main() { 
    int N; 
    printf("Entrez la taille de la chaine: "); 
    scanf("%d", &N); 
 
    char *chaine = ChargerChaine(N); 
    int longueur = Longueur(chaine); 
 
    char Tab[N], T[N]; 
    ChargerTab(chaine, Tab); 
 
    InverserTab(Tab, T, longueur); 
    printf("La chaine inversee est: "); 
    AfficherTab(T, longueur); 
 
    free(chaine);  
    return 0; 
}
