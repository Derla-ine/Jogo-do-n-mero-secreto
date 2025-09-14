
# 🔢 Jogo do Número Secreto

Um jogo simples e divertido desenvolvido em **JavaScript**, onde o objetivo é adivinhar um número secreto entre **1 e 10**.
Projeto criado e testado no **Visual Studio Code (VS Code)** 🖥️.

## 🚀 Tecnologias utilizadas

* HTML5 🌐
* CSS3 🎨
* JavaScript ⚡
* [ResponsiveVoice](https://responsivevoice.org/) para síntese de voz 🔊

---

## 🎮 Como funciona

1. O usuário deve escolher um número entre **1 e 10**.
2. O programa gera um número secreto aleatório.
3. A cada tentativa, o jogo informa se o número secreto é **maior** ou **menor**.
4. Ao acertar, o jogador recebe uma mensagem com a quantidade de tentativas.
5. É possível reiniciar a partida clicando em **Novo jogo**.

---

## 🖼️ Layout

Tela inicial do jogo:

```html
<h1>Adivinhe o <span class="container__texto-azul">número secreto</span></h1>
<p class="texto__paragrafo">Escolha um número entre 1 a 10</p>
<input type="number" min="1" max="10" class="container__input">
<div class="chute container__botoes">
    <button onclick="verificarChute()" class="container__botao">Chutar</button>
    <button onclick="reiniciarJogo()" id="reiniciar" class="container__botao" disabled>Novo jogo</button>
</div>
```

---

## 🧩 Lógica do jogo (app.js)

```javascript
let numeroLimite = 10;
let numeroSecreto = gerarNumeroAleatorio();
let tentativas = 1;

function verificarChute() {
    let chute = document.querySelector('input').value;
    
    if (chute == numeroSecreto) {
        exibirTextoNaTela('h1', 'Acertou!');
        let mensagemTentativas = `Você descobriu o número secreto com ${tentativas} tentativa(s)!`;
        exibirTextoNaTela('p', mensagemTentativas);
        document.getElementById('reiniciar').removeAttribute('disabled');
    } else {
        if (chute > numeroSecreto) {
            exibirTextoNaTela('p', 'O número secreto é menor');
        } else {
            exibirTextoNaTela('p', 'O número secreto é maior');
        }
        tentativas++;
        limparCampo();
    }
}
```

---

## ▶️ Como rodar o projeto

1. Clone o repositório:

   ```bash
   git clone https://github.com/seu-usuario/numerosecreto.git
   ```
2. Abra a pasta no **VS Code**.
3. Inicie o arquivo **index.html** no navegador.

---

## 📌 Funcionalidades extras

* 🔊 Feedback por voz com **ResponsiveVoice**.
* 🎨 Layout responsivo e estilizado com CSS.
* 🧠 O jogo não repete números até esgotar todas as opções (1 a 10).

---

## 👩‍💻 Autor

Desenvolvido com 💙 por **Derlaine**.

