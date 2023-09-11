//definindo um array de objetos chamado "produtos" que armazena informações sobre produtos
const produtos = [
    {
        id: "1",
        nome: "Informática para Internet: Interfaces Web II",
        prof: "Prof. Kelly",
        preco_de: 80,
        preco_por: 50,
        descricao: "O melhor curso de JavaScript",
        imagem: "./assets/1.png",

    },
    {
        id: "2",
        nome: "Gestão de Conteúdo Web II",
        prof: "Prof. Kelly",
        preco_de: 80,
        preco_por: 50,
        descricao: "O melhor curso de JavaScript",
        imagem: "./assets/3.png",
    }
];

//definindo uma função chamada "renderizaProdutos" que cria HTML para renderizar os produtos
function renderizaProdutos(){

//declara uma variavel para armazenar o HTML gerado
    let html = "";
    
    //iterando sobre o array de produtos para criar HTML para cada produto
    for (let i = 0; i < produtos.length; i++) {
    
    //chamando a função "criaProduto" para criar o HTML de um produto e adicionando ao HTML acumulado.
        html = html + criaProduto(produtos[i], i);
    }
    return html; //retorna o HTML gerado para todos os produtos
}

 //definindo uma função chamada "criaProduto" que cria a estrutura HTML para um produto
function criaProduto(produto, index) {
    return `
    <div class="curso">
        <img class='inicio' title="t" src="${produto.imagem}"/>
        <div class="curso-info">
            <h4>${produto.nome}</h4>
            <p>${produto.prof}</p>
            <p>${produto.descricao}</p>
        </div>
        <div class="curso-preco">
            <span class="preco_de">R$${produto.preco_de}</span>
            <span class="preco_por">R$${produto.preco_por}</span>
            <button class="btncar btn-add" data-index="${index}"></button>
        </div>
    </div>
    `;
}

//selecionando um elemento HTML com o ID "container"
const container = document.querySelector("#container")

//definindo o conteúdo do elemento "container" com o HTML gerado pela função "renderizaProdutos"
container.innerHTML = renderizaProdutos();
