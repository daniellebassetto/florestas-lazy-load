# 🌳 Exibição de Imagens de Floresta com Lazy Load 🌲

Este projeto é uma aplicação simples que exibe imagens de floresta 🌿 e implementa a técnica de **lazy loading** 💤 para otimizar o carregamento das imagens conforme são exibidas na tela.

## ✨ Funcionalidades Implementadas

- 🚀 **Carregamento preguiçoso (lazy loading):** As imagens só são carregadas quando estão prestes a entrar na tela.
- 🖼️ **Substituição dinâmica:** As imagens são carregadas em alta resolução automaticamente.

## 🛠️ Tecnologias Utilizadas

- 🌐 **HTML5**
- 🎨 **CSS3**
- 💻 **JavaScript (ES6+)**

## ⚙️ Como Funciona o Lazy Load

O **Intersection Observer** monitora as imagens 🖼️ enquanto você rola a página. Assim que uma imagem entra na área visível da tela, o código substitui o `src` por uma versão de alta resolução. 

Aqui está o código que faz a mágica acontecer: ✨

```javascript
const images = document.querySelectorAll(".image-container img");

const observer = new IntersectionObserver((entries, observer) => {
  entries.forEach((entry) => {
    if (!entry.isIntersecting) return;

    const image = entry.target;

    // Substitui o src para carregar uma versão de alta resolução
    image.src = image.src.replace("&w=10&", "&w=1000&");

    // Interrompe a observação desta imagem após carregar
    observer.unobserve(image);
  });
}, {});

images.forEach((image) => {
  observer.observe(image);
});
```

## 🚀 Como Usar

1. 🛠️ Clone o repositório:  
   ```bash
   git clone https://github.com/daniellebassetto/florestas-lazy-load.git
   ```
2. 🌟 Abra o arquivo `index.html` no seu navegador favorito.  
3. 🎉 Role a página e veja as imagens carregarem dinamicamente!

## 🤝 Contribuições

Contribuições são **muito bem-vindas**! 💡  
Abra uma *issue* ou envie um *pull request* para melhorias e sugestões. Vamos deixar esse projeto ainda mais incrível juntos! 🎉

## 📜 Licença

Este projeto está sob a **Licença MIT**. 📝  
Sinta-se livre para usá-lo, modificá-lo e compartilhá-lo! 😊


## 🌟 Obrigado por conferir este projeto! 🌟  
Se você gostou, deixe uma estrela ⭐ no repositório e compartilhe com seus amigos. 🚀
