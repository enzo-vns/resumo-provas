# Resumo de Provas — Unieuro

Repositório de estudos de alunos da **Unieuro** dos cursos de **Sistemas de Informação (SI)** e **Análise e Desenvolvimento de Sistemas (ADS)**.

Um espaço para compartilhar resumos, anotações e materiais de revisão, ajudar na preparação para as provas e aprender em conjunto ao longo da graduação.

## Escolha seu curso

A branch `main` contém somente esta apresentação. Os materiais estão organizados em duas branches de curso:

| Branch | Curso | Semestres |
| --- | --- | --- |
| [Análise e Desenvolvimento de Sistemas](https://github.com/enzo-vns/resumo-provas/tree/Analise-e-Desenvolvimento-de-Sistemas) | Análise e Desenvolvimento de Sistemas | 1º ao 5º |
| [Sistema de Informação](https://github.com/enzo-vns/resumo-provas/tree/Sistema-de-Informacao) | Sistemas de Informação | 1º ao 8º |

Ao entrar na branch do curso, você encontra um README e as pastas dos semestres. Dentro de cada semestre ficam seu README e as pastas `1o-bimestre/` e `2o-bimestre/`, organizadas por disciplina.

## Materiais do 3º semestre

Os materiais do **3º semestre** estão presentes em ambos os cursos: Engenharia de Requisitos, Estrutura de Dados e Banco de Dados. Cada bimestre também possui uma pasta **Redes de Computadores**, preparada para receber novos materiais.

Somente os materiais do 3º semestre são compartilhados entre os cursos. Os demais semestres estão preparados para receber conteúdos específicos de ADS ou SI.

## Como contribuir

Você pode contribuir com resumos, anotações, exercícios resolvidos e correções. O fluxo recomendado é criar uma cópia do repositório (fork), trabalhar em uma branch própria e abrir um pull request para revisão.

### 1. Escolha o curso e o semestre

Abra a branch do curso correto e confira o README do semestre para ver a organização e os materiais que já existem:

- **ADS:** branch `Analise-e-Desenvolvimento-de-Sistemas`, do 1º ao 5º semestre.
- **SI:** branch `Sistema-de-Informacao`, do 1º ao 8º semestre.

Cada semestre contém as pastas `1o-bimestre/` e `2o-bimestre/`. Coloque o material no bimestre e na disciplina correspondentes. No 3º semestre, a pasta de Redes chama-se `Redes de Computadores`.

### 2. Crie um fork

Na página do repositório, clique em **Fork** e crie uma cópia na sua conta do GitHub. O fork permite preparar a contribuição sem alterar diretamente o repositório original.

### 3. Clone seu fork

Copie a URL do seu fork e execute no terminal, substituindo `SEU-USUARIO` pelo seu nome de usuário do GitHub:

```bash
git clone https://github.com/SEU-USUARIO/resumo-provas.git
cd resumo-provas
git remote add upstream https://github.com/enzo-vns/resumo-provas.git
git fetch upstream
```

`origin` aponta para seu fork. `upstream` aponta para o repositório original.

### 4. Crie uma branch para sua contribuição

Use como base a branch do curso e crie uma branch própria. Escolha **uma** das opções abaixo:

Para ADS:

```bash
git switch -c minha-contribuicao --no-track upstream/Analise-e-Desenvolvimento-de-Sistemas
```

Para SI:

```bash
git switch -c minha-contribuicao --no-track upstream/Sistema-de-Informacao
```

Você pode trocar `minha-contribuicao` por um nome curto que descreva a mudança, por exemplo, `resumo-banco-de-dados`.

### 5. Adicione ou corrija o material

Edite ou crie arquivos dentro da pasta correta. Por exemplo, um resumo de Redes no 3º semestre e 1º bimestre de SI ficaria em:

```text
3o-semestre/1o-bimestre/Redes de Computadores/
```

Prefira arquivos Markdown (`.md`) para resumos e anotações. Use títulos e subtítulos para organizar o conteúdo, confira a ortografia e inclua links ou fontes quando usar referências. Dê ao arquivo um nome claro, como `sub-redes-e-enderecamento-ip.md`.

Se criar uma disciplina que ainda não tem pasta, use um nome legível, com iniciais maiúsculas e espaços, sem numeração ou hífens. Git não mantém pastas vazias; inclua um arquivo de material ou um `.gitkeep` para registrar a pasta.

Compartilhe apenas materiais que você tenha autorização para publicar. Não inclua dados pessoais, senhas ou chaves de acesso.

### 6. Revise e registre as alterações

Confira quais arquivos mudaram e verifique erros simples de formatação:

```bash
git status
git diff --check
git diff
```

Quando estiver satisfeito, adicione e registre sua contribuição:

```bash
git add "3o-semestre/1o-bimestre/Redes de Computadores/sub-redes-e-enderecamento-ip.md"
git commit -m "docs: adiciona resumo de redes"
```

Adapte o caminho e a mensagem do commit aos arquivos que você alterou.

### 7. Envie sua branch para o fork

```bash
git push -u origin minha-contribuicao
```

### 8. Abra um pull request

No GitHub, abra um pull request do seu fork para `enzo-vns/resumo-provas`. Selecione como branch de destino a branch do **mesmo curso** que usou como base:

- `Analise-e-Desenvolvimento-de-Sistemas` para ADS;
- `Sistema-de-Informacao` para SI.

Não use `main` como destino dos materiais dos cursos. No título, explique a contribuição. Na descrição, informe o semestre, bimestre, disciplina e um resumo do que mudou. Confira os arquivos exibidos no pull request antes de enviá-lo.

### 9. Acompanhe a revisão

Responda a comentários e faça as correções solicitadas na mesma branch. Depois, envie as alterações novamente:

```bash
git add .
git commit -m "docs: ajusta resumo após revisao"
git push
```

As novas alterações aparecerão no mesmo pull request. A contribuição entra no repositório quando o pull request for aprovado e integrado.
Correções, exemplos e novos resumos são bem-vindos!
