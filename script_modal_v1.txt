// Função para abrir a janela modal com a avaliação do filme
function openModal(film) {
    // Seleciona o elemento modal
    var modal = document.querySelector(".modal");
    // Seleciona o elemento que contém o conteúdo da modal
    var modalContent = document.querySelector(".modal-content");
    // Seleciona o elemento que fecha a modal
    var modalClose = document.querySelector(".modal-close");
    // Mostra a modal
    modal.style.display = "block";
    // Limpa o conteúdo da modal
    modalContent.innerHTML = "";
    // Cria um elemento h2 com o título do filme
    var h2 = document.createElement("h2");
    h2.textContent = film;
    // Adiciona o elemento h2 ao conteúdo da modal
    modalContent.appendChild(h2);
    // Cria um elemento p com a avaliação do filme
    var p = document.createElement("p");
    // Gera uma avaliação aleatória para o filme
    p.textContent = generateReview(film);
    // Adiciona o elemento p ao conteúdo da modal
    modalContent.appendChild(p);
    // Adiciona um evento de clique ao botão que fecha a modal
    modalClose.addEventListener("click", function() {
    // Esconde a modal
    modal.style.display = "none";
    });
    }
    
    // Função para gerar uma avaliação aleatória para o filme
    function generateReview(film) {
    // Cria um array com algumas opiniões possíveis
    var opinions = [
    "Eu gostei muito desse filme, achei que foi bem produzido e dirigido.",
    "Eu não gostei desse filme, achei que foi mal escrito e sem graça.",
    "Eu achei esse filme mediano, teve alguns momentos bons e outros ruins.",
    "Eu adorei esse filme, foi uma das melhores experiências que eu já tive no cinema.",
    "Eu odiei esse filme, foi uma perda de tempo e dinheiro.",
    "Eu me surpreendi com esse filme, foi melhor do que eu esperava.",
    "Eu me decepcionei com esse filme, foi pior do que eu esperava.",
    "Eu achei esse filme divertido, mas não muito original.",
    "Eu achei esse filme chato, mas bem feito tecnicamente.",
    "Eu achei esse filme incrível, foi uma obra-prima da sétima arte."
    ];
    // Cria um array com algumas notas possíveis
    var ratings = [
    "1/10",
    "2/10",
    "3/10",
    "4/10",
    "5/10",
    "6/10",
    "7/10",
    "8/10",
    "9/10",
    "10/10"
    ];
    // Escolhe uma opinião e uma nota aleatórias
    var opinion = opinions[Math.floor(Math.random() * opinions.length)];
    var rating = ratings[Math.floor(Math.random() * ratings.length)];
    // Retorna a avaliação do filme no formato "Opinião. Nota."
    return opinion + " " + rating + ".";
    }