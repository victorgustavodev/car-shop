## Classic Car Store 🚗
# Totalmente desenvolvido para fins de prática e estudo.

Bem-vindo ao **Classic Car Store**, uma aplicação desenvolvida com Vue.js para exibir uma seleção de carros clássicos. Este projeto utiliza conceitos fundamentais do Vue.js, como componentes, diretivas, propriedades reativas e computadas, além de estilização com Tailwind CSS.

## Funcionalidades

- **Seleção de Carros**: O usuário pode selecionar diferentes carros clássicos de uma lista.
- **Exibição Dinâmica**: As informações do carro selecionado, como nome, ano, fabricante, preço e imagem, são exibidas dinamicamente.
- **Estilização Personalizada**: O fundo e o menu lateral mudam de cor com base no carro selecionado, utilizando propriedades reativas.
- **Responsividade**: A interface é responsiva e adaptada para diferentes tamanhos de tela.
- **Componentização**: A aplicação é dividida em componentes reutilizáveis, como `CarList` e `CarDetails`, para facilitar a manutenção e escalabilidade.
- **Uso de Props**: Os componentes utilizam `props` para receber dados de forma dinâmica, promovendo maior flexibilidade e reutilização.

## Tecnologias Utilizadas

- **Vue.js 3**: Framework JavaScript progressivo para construção de interfaces de usuário.
- **Tailwind CSS**: Framework CSS utilitário para estilização rápida e responsiva.
- **JavaScript ES6**: Utilizado para lógica e manipulação de dados.
- **Webpack**: Gerenciador de pacotes e bundler configurado pelo Vue CLI.

## Estrutura do Projeto

A estrutura principal do projeto é a seguinte:

```
src/
├── App.vue          # Componente principal da aplicação
├── main.js          # Arquivo de entrada para inicializar o Vue
├── components/      # Componentes reutilizáveis como CarList e CarDetails
├── assets/          # Imagens dos carros e outros recursos estáticos
public/
├── index.html       # Arquivo HTML principal
```

## Conceitos do Vue.js Aplicados

- **Data Binding**: Utilização de `v-model` para vincular o valor do carro selecionado ao estado da aplicação.
- **Diretivas**: Uso de `v-for` para renderizar dinamicamente a lista de carros e `v-bind` para vincular atributos.
- **Propriedades Computadas**: A propriedade `selectedCar` é calculada dinamicamente com base no carro selecionado.
- **Reatividade**: Alterações no estado da aplicação atualizam automaticamente a interface do usuário.
- **Componentização**: Estrutura modular com componentes como `CarList` e `CarDetails`.
- **Props**: Os componentes recebem dados dinamicamente através de `props`, permitindo maior flexibilidade e reutilização.

## Como Executar o Projeto

### Pré-requisitos

- Node.js instalado na máquina.
- Gerenciador de pacotes npm ou yarn.

### Passos

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/classic-car-store.git
   cd classic-car-store
   ```

2. Instale as dependências:
   ```bash
   npm install
   ```

3. Inicie o servidor de desenvolvimento:
   ```bash
   npm run serve
   ```

4. Acesse a aplicação no navegador:
   ```
   http://localhost:8080
   ```

## Personalização

Os dados dos carros estão localizados no arquivo `App.vue` e podem ser facilmente alterados para adicionar ou modificar os carros exibidos. Além disso, os componentes podem ser estendidos ou personalizados para atender a diferentes necessidades.

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests.

## Licença

Este projeto está licenciado sob a [MIT License](LICENSE).

---

Desenvolvido com ❤️ e Vue.js.
