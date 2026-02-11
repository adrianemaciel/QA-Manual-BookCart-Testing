## 📚 Projeto de Testes Manuais - Book Cart

### 📌 Objetivo dos Testes

O objetivo deste ciclo de testes é validar as funcionalidades de busca, filtragem e persistência de dados na plataforma [Book Cart](https://bookcart.azurewebsites.net/). O foco principal foi garantir que a experiência de navegação e a integridade das requisições de backend estejam alinhadas às expectativas de um e-commerce funcional e seguro.

---

### 📊 Plano de Testes e Cenários

Abaixo estão os cenários documentados durante a fase de Mapeamento de Funcionalidades e Filtros.

| ID  | Funcionalidade | Caso de Teste                     | Cenário (BDD)                                                                                                                            | Status |
| :-- | :------------- | :-------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------- | :----: |
| 1   | Busca          | Pesquisa em "All Categories"      | **Dado** que o usuário está na home **Quando** realizar uma busca global **Então** o sistema deve retornar os livros correspondentes.    | ❌ NOK |
| 2   | Filtros        | Persistência da categoria         | **Dado** que uma categoria específica está selecionada **Quando** clicar em pesquisar **Então** a categoria deve permanecer selecionada. | ❌ NOK |
| 3   | Filtros        | Funcionalidade do Slider de Preço | **Dado** que o usuário interage com o seletor de preço **Então** o componente deve atualizar os valores e filtrar a lista.               | ❌ NOK |
| 4   | Interface (UI) | Alinhamento e Leitura de Preço    | **Dado** que o filtro de preço é exibido **Então** o valor mínimo deve estar à esquerda e as etiquetas devem ser legíveis.               | ❌ NOK |

---

### 🔍 Principais Descobertas Técnicas

Durante a execução, foram identificados problemas que impactam diretamente a usabilidade e a estabilidade do sistema:

- Falha Oculta de Backend: Identificação de Erro 500 (Internal Server Error) mascarado por uma mensagem de "No books found" com Status 200 no frontend.

- Regressão de Filtros: O sistema reseta o estado da categoria selecionada para o padrão ("All Categories") após qualquer ação de busca.

- Componente de UI Quebrado: O slider de preço apresenta labels em linguagem ilegível, valores de mínimo e máximo invertidos e está funcionalmente travado.

---

### 🛠️ Tecnologias e Metodologias

- QA Manual: Testes exploratórios e funcionais.

- BDD (Behavior Driven Development): Escrita de cenários focada no comportamento do usuário.

- Chrome DevTools: Inspeção de Network/Rede para validação de Status Codes e Payloads.

> Nota: Para o detalhamento completo dos passos para reproduzir cada falha e as capturas de tela, consulte o [Relatório de Bugs](./BUG_REPORTS.md).
