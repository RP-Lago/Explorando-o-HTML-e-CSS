<!-- 

No vídeo anterior, você aprendeu como alinhar elementos através do justify-content, comando responsável por justificar, formatando o posicionamento de acordo com o requisito do desenvolvedor.

Agora, imagine que você recebeu um código pronto, o qual, por apresentar erros, não está funcionando (analise-o com atenção):

main {
    display: flexbox;
    justify-content: center;
}
Copiar código
Além do código, também enviaram imagens de como está e como deveria ser o projeto:

Como está:
Print do conteúdo da tag main demarcado por um background-color cinza. Dentro do main possui uma coluna com dois quadrados, um preto e um vermelho. Esses quadrados estão grudados e o vermelho está saindo do limite do main na parte inferior da margem.

Como deveria ser:
Print do conteúdo da tag main demarcado por um background-color cinza. Dentro do main possui dois quadrados, um preto e um vermelho, alinhados horizontalmente. Esses quadrados estão separados por um espaço no meio e ambos estão dentro do limite do main.

Analise o código e as imagens acima.

Como você pode corrigir o código? -->



### **Problemas no código**
1. **Erro na propriedade `display`:** O valor `flexbox` está incorreto. O valor correto para ativar o comportamento Flexbox é `flex`.  
2. **Erro no alinhamento dos itens:** Atualmente, os itens não estão configurados para se alinhar horizontalmente nem com espaçamento apropriado. A propriedade `justify-content: center;` centraliza os itens no eixo principal, mas o layout não se ajusta como esperado por outros fatores, como margens ou propriedades incorretas nos itens.

---

### **Correção do código**

Aqui está a versão corrigida para alinhar os dois quadrados horizontalmente com o espaçamento correto:

```css
main {
    display: flex; /* Corrige o valor para Flexbox */
    justify-content: space-between; /* Distribui os itens com espaço entre eles */
    align-items: center; /* Centraliza os itens verticalmente */
    height: 100vh; /* Garante que o main ocupe a altura total da tela */
    background-color: gray; /* Para visualizar os limites do main */
    padding: 20px; /* Evita que os itens grudem nas bordas */
    box-sizing: border-box; /* Garante que padding não expanda o main */
}

main .quadrado {
    width: 100px; /* Largura de cada quadrado */
    height: 100px; /* Altura de cada quadrado */
}

main .quadrado-preto {
    background-color: black; /* Cor preta para o primeiro quadrado */
}

main .quadrado-vermelho {
    background-color: red; /* Cor vermelha para o segundo quadrado */
}
```

---

### **HTML correspondente**
Certifique-se de que o HTML esteja configurado corretamente para o layout:

```html
<main>
    <div class="quadrado quadrado-preto"></div>
    <div class="quadrado quadrado-vermelho"></div>
</main>
```

---

### **Explicação das alterações**
1. **`display: flex;`**: Habilita o Flexbox para o elemento `<main>`, corrigindo o uso errado de `flexbox`.
2. **`justify-content: space-between;`**: Alinha os itens horizontalmente com espaço igual entre eles.
3. **`align-items: center;`**: Centraliza os itens verticalmente no eixo cruzado (altura do container).
4. **`padding: 20px;`**: Adiciona um espaço interno ao `<main>` para evitar que os quadrados grudem nas bordas.
5. **`box-sizing: border-box;`**: Garante que o padding não aumente o tamanho do `<main>`.
6. **Altura e largura dos quadrados**: Garante dimensões consistentes para ambos os elementos.

---

### **Resultado esperado**
- Os dois quadrados estarão **alinhados horizontalmente** no centro do `<main>`.
- Ambos terão o mesmo tamanho, estarão separados por um espaço proporcional e não ultrapassarão os limites do `<main>`.

Se precisar de mais ajuda ou de ajustes adicionais, é só avisar!
