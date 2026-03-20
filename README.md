# 📝 Simulado - Conhecimentos Específicos

Repositório dedicado ao desenvolvimento de uma aplicação web de simulado para Conhecimentos Especifícos  **Profissional de Administração**. O foco do projeto é oferecer uma experiência de estudo dinâmica, com questões de Ética, Direito Administrativo, CF/88, LGPD, LAI e Redação Oficial.

---

## 🚀 Funcionalidades Implementadas

*   **Embaralhamento Inteligente (Double Shuffle):** 
    *   As questões são embaralhadas a cada nova tentativa.
    *   As alternativas (opções) dentro de cada questão também são embaralhadas, evitando a memorização por posição.
*   **Correção Dinâmica:** Lógica de validação baseada em comparação de strings, permitindo que o gabarito permaneça correto mesmo com a mudança de ordem das alternativas.
*   **Cálculo de Nota Escalar:** Sistema que converte o número de acertos em uma nota de **0 a 10.0**, seguindo o padrão acadêmico.
*   **Interface Institucional:** Design inspirado na identidade visual da universidade (Azul Marinho e Dourado).
*   **UX Otimizada:** 
    *   Rodapé fixo com contador de questões respondidas.
    *   Botões com efeitos de *hover* e transições suaves.
    *   Revisão detalhada com feedback visual (Verde para acerto / Vermelho para erro).

---

## 🛠️ Tecnologias Utilizadas

*   **React.js:** Biblioteca principal para construção da interface.
*   **JavaScript (ES6+):** Lógica de embaralhamento e manipulação de arrays.
*   **CSS-in-JS (Inline Styles):** Estilização dinâmica e responsiva.
*   **Vite:** Tooling para um desenvolvimento rápido e build otimizado.

---

## 📂 Estrutura do Projeto

```text
├── src/
│   ├── data/
│   │   └── questions.js   # Banco de dados com as 70 questões e gabaritos
│   ├── App.jsx            # Componente principal com a lógica do simulado
│   └── main.jsx           # Ponto de entrada da aplicação
├── public/                # Ativos estáticos
└── package.json           # Dependências e scripts do projeto
```

---

## 🧠 Desafios Técnicos Resolvidos

### Inicialização Lazy do Estado
Para evitar o erro de performance `react-hooks/set-state-in-effect` (cascading renders), o embaralhamento inicial foi implementado via *Lazy Initializer* no `useState`:
```javascript
const [questions, setQuestions] = useState(() => shuffleAll(questionsData));
```

### Algoritmo de Embaralhamento
Utilização do método `.sort(() => Math.random() - 0.5)` para garantir uma distribuição aleatória tanto no array de objetos (questões) quanto nos arrays aninhados (opções).

### Efeitos de Hover em Estilos Inline
Implementação de interatividade em botões utilizando os eventos `onMouseEnter` e `onMouseLeave` para manipular o DOM sem a necessidade de arquivos CSS externos.

---

## 🏁 Como Rodar o Projeto

1. Clone o repositório:
   ```bash
   git clone https://github.com/EsmeraldoCarneiro/Aplicacao-web-de-simulado-para-estudo-de-Nocoes-de-Informatica.git
   ```

2. Instale as dependências:
   ```bash
   npm install
   ```
3. Inicie o servidor de desenvolvimento:
   ```bash
   npm run dev
   ```

---

## 📄 Licença
Este projeto foi desenvolvido para fins de estudo e preparação para o concurso.

---

**Desenvolvido por Esmeraldo Junior** 🎓

*Focado em excelência e produtividade.*
