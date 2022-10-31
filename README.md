<h1 align="center">
Lista 🎎<br>
(Estrutura de Dados)

## Introdução

> Uma lista encadeada é uma representação de uma sequência de objetos, todos do mesmo tipo, na memória RAM (= random access memory) do computador. Cada elemento da sequência é armazenado em uma célula da lista: o primeiro elemento na primeira célula, o segundo na segunda, e assim por diante.


## Conceito de Lista Encadeada

- É uma coleção de nós que formam uma ordem linear. Sendo que cada nó é um objeto que armazena a referência do próximo nó, mais um dado ou objeto (Java).

- O primeiro nó é chamado de cabeça (head), enquanto o último nó é chamado de cauda (tail).

## Representação gráfica da lista

<img src="https://i.imgur.com/M7biZTl.png">

## Criando o nó

```
public class No{
    private String elemento;
    private No proximo; 
    private No cauda;
    
    public No(String elemento, No proximo) {
         this.elemento = elemento;
         this.proximo = proximo;
    }
    
    public String getElemento() { 
         return elemento; 
    }

    public void setElemento(String elemento) { 
         this.elemento = elemento;
    }
    
    public No getProximo() {
         return proximo;
    }
    
    public void setProximo(No proximo)
        this.proximo = proximo;
    }
    
    public No getCauda(){
        return cauda;
    }
    
    public void setCauda(No cauda) { 
        this.cauda = cauda;
    }
}
```

## Criando a Lista

```
public class ListaEncadeadaSimples{ 
    No cabeca = null;
    Integer tamanho = 0;
    No cauda = null;
}
```

## Adicionar o Primeiro Elemento na Lista

```
public void adicionaPrimeiroElemento(No no){
     //lista vazia
     if (tamanho == 0){ 
         cauda = no;
         cabeca = no;
     }else{ 
         no.setProximo(cabeca);
         cabeca = no;
     }
     tamanho++;
}
```

## Adicionar um elemento na Lista

```
public void adicionaElemento(No no){
    if(tamanho == 0){
       cabeca.setProximo(no);
       cabeca.setProximo(no);
    }else{ 
        cauda.setProximo(no);
        cauda = no;
    }
    tamanho++;
}
```
## Verificar se a posição está ocupada

```
private boolean posicaoOcupada(int posicao){ 
    return posicao >= 0 && posicao < tamanho;
}
```

## Verificar se a posição está ocupada

```
private No pegaPosicao(int posicao) { 
    if(!this.posicaoOcupada(posicao)){
        throw new IllegalArgumentException("Posição não existe");
    }
    No atual = cabeça;
    for (int i = 0; < posicao-1; i++) {
        atual = atual.getProximo(); 
    }
    return atual;
}
```

## Pegar o nó pela posição na lista

```
private No pegaPosicao(int posicao) {
    if (!this.posicaoOcupada(posicao)) { 
        throw new IllegalArgumentException("Posição não existe");
    }
    No atual = cabeca;
    for (int i = 0; i < posicao-1; i++){ 
         atual = atual.getProximo();
    }
    return atual;
}
```

## Pegar um elemento pela posição 

```
public String pegaElemento(int posicao){ 
    return this.pegaNo(posicao).getElemento();
}
```

## Remover a cabeça da Lista

```
public void removeCabeca() {
    if (!this.posicaoOcupada(0)) {
        throw new IllegalArgumentException("Posição não existe");
        }
     cabeca = cabeca.getProximo();
     tamanho--;
     if (this.tamanho == 0) {
         this.cauda = null;
     }
 }
```

## Exibir a lista

```
public String toString() {
   // Verificando se a Lista está vazia
   if (tamanho == 0){ 
        return "[]";
   }
   StringBuilder builder = new StrigBuilder("[");
   No atual = cabeça;
   // Percorrendo até o penúltimo elemento.
   for (int i = 0; i < tamanho - 1; i++) {
        builder.append(atual.getElemento());
        builder.append(", ");
        atual = atual.getProximo();
   }
   // Último elemento
   builder.append(atual.getElemento());
   builder.append("]");
   return builder.toString();
}
```


<div align="center">
    © Material fornecido por <a href="https://br.linkedin.com/in/icarofreitas">Prof° Ícaro de Paula Freitas</a></p>
</div>
