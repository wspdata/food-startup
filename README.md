# Startup Alimentícia — Teste A/A/B e Análise de Funil de Conversão

## Descrição do Projeto
Projeto de análise de dados aplicado a uma startup de produtos alimentícios. O objetivo foi analisar o comportamento dos usuários no aplicativo da empresa e avaliar o impacto de uma mudança de design (fonte) por meio de um experimento controlado A/A/B — verificando se a alteração influenciava o comportamento dos usuários ao longo do funil de conversão.

---

## Metodologia
1. **Pré-processamento dos dados**
   - Renomeação de colunas para padrão `snake_case`, correção de tipos de dados e conversão de timestamps Unix para formato `datetime`.
2. **Análise Exploratória de Dados (EDA)**
   - Análise do período coberto pelos dados, distribuição de eventos por hora, identificação de dados esparsos (antes de 01/08/2019) e validação do corte temporal com cálculo de perda de eventos e usuários.
3. **Análise do Funil de Eventos**
   - Mapeamento das etapas do funil de conversão, cálculo de taxa de conversão entre etapas e proporção de usuários que completam o caminho completo.
4. **Teste Estatístico A/A/B**
   - Validação dos grupos de controle (A/A) por teste de proporções z; testes A/B comparando o grupo experimental (248) com cada grupo de controle individualmente e com os controles combinados (246 + 247); aplicação da correção de Bonferroni para controle de falsos positivos.

---

## Principais Insights

- **Funil de conversão:** 98,47% dos usuários chegam à tela principal (`MainScreenAppear`), mas apenas 50,33% avançam para o carrinho — a maior queda de todo o funil. Entre carrinho e pagamento, a conversão é alta: 94,78%. No total, **47,70% dos usuários completam o funil inteiro**.

- **Validação A/A:** Os grupos de controle 246 e 247 se mostraram estatisticamente equivalentes em todos os eventos (p-valores entre 0,11 e 0,94), confirmando que o experimento estava bem calibrado antes da análise A/B.

- **Resultado do Teste A/B:** Nenhum dos eventos analisados apresentou diferença estatisticamente significativa entre o grupo experimental (fonte nova) e os controles. Os p-valores ficaram todos acima de 0,05, e mesmo após a correção de Bonferroni (α = 0,0025 para 20 testes), os resultados permanecem inalterados. **A mudança de fonte não impactou o comportamento dos usuários.**

---

## 📊 Estrutura do Funil

| Etapa                      | Usuários | Proporção |
|----------------------------|----------|-----------|
| `MainScreenAppear`         | 7.419    | 98,47%    |
| `OffersScreenAppear`       | 4.593    | 60,96%    |
| `CartScreenAppear`         | 3.734    | 49,56%    |
| `PaymentScreenSuccessful`  | 3.539    | 46,97%    |
| `Tutorial`                 | 840      | 11,15%    |

---

## 📂 Conteúdo do Repositório

- **Notebook (.ipynb):** análise completa, incluindo pré-processamento, EDA, análise de funil, testes estatísticos e conclusões
- **log_exp_us (.csv):** logs de eventos dos usuários no aplicativo
- **README (.md):** este arquivo

---

## Tecnologias e Bibliotecas

- Linguagem: **Python**
- Bibliotecas: **pandas**, **numpy**, **matplotlib**, **scipy**
- Notebook: **Jupyter Notebook**

---

## Contato

Willian De Souza Pereira — ws13292@gmail.com

LinkedIn: https://linkedin.com/in/willian-de-souza-pereira-b69109202

## Licença

Este repositório está disponível para estudo e demonstração. Sinta-se à vontade para clonar, adaptar e abrir *issues* com dúvidas ou sugestões.
