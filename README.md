# "Bloco" de anotações e resumos em meus estudos sobre o Java e afins
#####1. Me surgiu a dúvida de uma expressão que o professor usa para criarmos uma exception de ResponseStatus que é a expressão **feature Lambda**:
![foto](https://img-a.udemycdn.com/redactor/raw/q_and_a/2020-12-02_19-22-46-77f0b6a7257fc13ea6ff0de138001a47.png?KeRdmDovhaK2QUobtK0rjPXKuHISWxeRpBPhXx9ZJiYMqtQWEKbaisVNNKk2EJgNRB9TnukEtKgVXSH4CAiu7IrMsF7xeRNMjD0_9xODy_WFe0-nWg1_Vvhs06sEwDQC7Pbf-9WVBr-1XVaq013fMzTyEx-RgShG_N1AeDi1TmHN6Bs2NC2Hi2apwJQ)

Essa expressão é uma feature que surgiu a partir do Java 8, conhecida como **LAMBDA**.

No caso do exemplo que coloquei, o método *orElseThrow* recebe como parâmetro uma implementação de `Supplier<Throwable>`.

Supplier é uma interface funcional, ou seja, uma interface de apenas um método, e as interfaces funcionais permitem que, ao invés de instanciarmos uma classe anônima, como por exemplo:
```java
new Supplier<Throwable>() {
    @Override
    public Throwable supply(){
        return new ResponseStatusException(HttpStatus.NOT_FOUND);
    }
}
```
Por isso usei ela contraída como lambda, que fica bem mais simples e clean:
```
() -> new ResponseStatusException(HttpStatus.NOT_FOUND)
```
[Artigo sobre o uso de LAMBDA que foi introduzida no Java 8](https://blog.tecsinapse.com.br/stream-api-e-fun%C3%A7%C3%B5es-lambda-no-java-8-9941e8ae95d8)

Já o parâmetro vazio que passei antes do LAMBDA **" () -> "** indica que o método não recebe parâmetros, e é assim na interface Supplier. Seu método supply() não tem argumentos, por isso coloquei assim... Quando a interface funcional recebe algum parametro, declaramos como: ``` (value) -> value.toString() ```

***

#####2. Erro Angular "Object is posibly 'null'";
Dúvida que me gerou e não sabia como resolver, eu sabia que o objeto poderia ser nulo mas não sabia como dizer para o Angular resolver isso. Foi ai que encontrei a solução em um operador chamado Elvis(com símbolo de interregação ?). Esse operador fornece uma maneira de fazermos uma navegação segura entre  os objetos(por exemplo, se for nulo o objeto dará erro, elvis evita isso). Quando colocamos essa interrogação depois da nossa variável ou objeto que pode ter valor nulo, ele faz uma lógica parecida com o operador ternário. Esse operador é usado para acessar um atributo de um objeto, apenas quando o objeto não é nulo. Enquanto ele for nulo, nada é acessado(renderizará o template como um valor vazio).
Ex do Elvis Operator:
```html
<h3>Detalhes do Carro</h3>

<p>ID: {{ carro?.id }}</p>
<p>Marca: {{ carro?.marca }}</p>
<p>Modelo: {{ carro?.modelo }}</p>
<p>Cor: {{ carro?.cor }}</p>
```

***

.
 
