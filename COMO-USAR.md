# Telão do Ranking · Vigga — evento 12/08/2026

Um único arquivo faz tudo: **`index.html`**. Ele lê uma planilha do Google e mostra o
ranking na TV, atualizando sozinho a cada ~4 segundos — sem servidor, sem instalação,
sem recarregar página. Funciona até aberto de um pendrive.

---

## Antes do evento (5 minutos)

### 1. Crie a planilha de resultados
No Google Sheets, crie uma planilha assim:

| A (nome)            | B (tempo em segundos) |
|---------------------|----------------------|
| Nome do barbeiro    | 32,45                |

- Pode ter cabeçalho na primeira linha (o telão ignora sozinho).
- **Decimais sempre com vírgula: `32,45`.** Em planilha em português, digitar com
  ponto (`32.45`) faz o Google interpretar a célula como data ou como milhar — o
  telão tem proteção para o caso da data, mas a vírgula é o caminho garantido.
  `1:32` (1min32s) também vale.
- **Blindagem total (recomendado):** antes do evento, selecione a coluna B inteira →
  **Formatar → Número → Texto simples**. Assim o Google não interpreta nada e
  qualquer jeito de digitar (`3,91`, `3.91`, `1:32`) chega certo no telão.

### 2. Compartilhe a planilha
**Compartilhar → Acesso geral → "Qualquer pessoa com o link" → Leitor.**
Sem isso o telão não consegue ler os dados.

### 3. Conecte o telão
1. Abra o `index.html` com dois cliques (Chrome de preferência).
2. Cole o link da planilha (o mesmo da barra do navegador).
3. Escolha o critério do ranking:
   - **Menor tempo** — tempo mais baixo fica em 1º; ou
   - **Mais perto do alvo** — quem chegar mais perto do tempo alvo fica em 1º
     (informe o alvo em segundos).
4. Ajuste o título se quiser e clique em **Abrir telão**.

A configuração fica salva no navegador — na próxima vez já abre direto no ranking.

---

## Durante o evento

- A equipe **só preenche a planilha** (do celular ou notebook): nome na coluna A,
  tempo na coluna B. Em poucos segundos o resultado entra no telão com animação.
- **Errou?** Corrija ou apague a linha na planilha — o telão se ajusta sozinho.
- **Novo líder** dispara celebração com confete automaticamente.
- Tecla **C** repete a celebração do líder atual (bom para o apresentador animar o público).
- **Dois cliques na tela** = tela cheia.
- O ranking mostra pódio (top 3) fixo + lista do 4º em diante. Com muitos participantes,
  a lista gira de página sozinha a cada 9s — ninguém fica de fora.

---

## Como exibir na TV

Em ordem de preferência:

1. **Notebook ligado na TV por HDMI** (mais confiável): abra o telão, tela cheia, pronto.
2. **Chromecast**: abra o telão no Chrome e transmita a aba (⋮ → Transmitir).
3. **Navegador da própria TV**: possível, mas exige levar o arquivo até a TV — prefira as opções acima.

> **Internet:** o telão precisa de internet para ler a planilha do Google.
> Se a conexão cair, ele avisa ("sem conexão · mostrando últimos dados") e continua
> exibindo o último ranking; ao voltar a conexão, atualiza sozinho.

---

## Testar sem planilha

Na tela inicial, clique em **"Ver demonstração com dados de exemplo"** — o telão roda
com participantes fictícios chegando aos poucos, incluindo a celebração de novo líder.

---

## Configuração por link (avançado)

Dá para montar um link que já abre configurado (útil para deixar tudo pronto num atalho):

```
index.html?planilha=ID_DA_PLANILHA&criterio=alvo&alvo=5&titulo=Desafio da Barbearia
```

| Parâmetro   | O que faz                                          |
|-------------|----------------------------------------------------|
| `planilha`  | ID da planilha (o trecho longo do link)            |
| `gid`       | ID da aba, se não for a primeira                   |
| `criterio`  | `menor` (padrão) ou `alvo`                         |
| `alvo`      | tempo alvo em segundos (modo alvo)                 |
| `titulo`    | título exibido no topo                             |
| `demo`      | modo demonstração (`demo=25` = 25 participantes)   |

Para trocar a configuração depois: mexa o mouse e clique em **"‹ Voltar à
configuração"** (canto inferior esquerdo), na engrenagem (canto inferior direito),
ou aperte **Esc**.

---

## Conferência do briefing

- [x] Cadastro aceita nome + tempo e a equipe usa sem treinamento (é uma planilha Google)
- [x] Resultado novo aparece no telão sozinho, sem recarregar (leitura a cada ~4s)
- [x] Ranking ordena pelo critério — **os dois critérios prontos** (menor tempo / mais perto do alvo)
- [x] Registro errado pode ser corrigido/apagado na planilha durante o evento
- [x] Layout para TV: fontes grandes, contraste alto, tela cheia (testado em 1920×1080)
- [x] Identidade visual da Vigga (cores do site: verde `#244545`, dourado `#FFCD70`/`#D5AD63`; tipografia geométrica)
- [x] Testado com 25 participantes — a lista pagina sozinha, ninguém é cortado
- [ ] **Pendente com o cliente:** confirmar o critério (menor tempo × mais perto do alvo) e nº de barbeiros
- [ ] **Pendente com o local:** como a TV vai exibir (recomendado: notebook + HDMI) e internet estável
