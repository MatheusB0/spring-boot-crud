### Convenções de nomeação
Os arquivos de arquitetura devem usar nomes descritivos, em letras minúsculas e no formato `kebab-case` (palavras separadas por hífens). O nome deve indicar claramente o conteúdo ou a finalidade do arquivo.
### Politica de versionamento
O projeto adota o **Versionamento Semântico (SemVer)** para identificar suas versões e comunicar o impacto das alterações realizadas. O número da versão segue o formato `MAJOR.MINOR.PATCH`, por exemplo, `2.4.1`.
- **MAJOR**: incrementado quando são introduzidas alterações incompatíveis com versões anteriores.
- **MINOR**: incrementado quando são adicionadas funcionalidades compatíveis com versões anteriores. Ao incrementá-lo, o número de `PATCH` é redefinido para zero.
- **PATCH**: incrementado quando são feitas correções compatíveis com versões anteriores, sem adicionar novas funcionalidades. Ao incrementá-lo, o número de `MINOR` é mantido.
  Versões em desenvolvimento, ainda não estáveis, podem ser identificadas com um sufixo de pré-lançamento, como `1.2.0-alpha.1`. Informações adicionais de compilação podem ser indicadas após o sinal `+`, como em `1.2.0+build.45`; esses metadados não alteram a precedência da versão.
  Enquanto a versão principal for `0` — por exemplo, `0.8.2` — a API ou o produto pode estar em desenvolvimento inicial, e alterações incompatíveis podem ocorrer. A partir da versão `1.0.0`, o projeto considera sua interface pública estável e aplica as regras de compatibilidade descritas acima.
  **Documentação oficial:** https://semver.org/lang/pt-BR/
### Política de branching
#### Branch principal
A branch `main` representa a linha principal de desenvolvimento e deve permanecer estável, com código revisado e validado pelas verificações automatizadas disponíveis no projeto. Alterações devem ser integradas por meio de _pull requests_, sem commits diretos nessa branch.
As versões disponibilizadas são identificadas por tags associadas aos respectivos commits na `main`, seguindo o padrão de versionamento semântico adotado pelo projeto.
#### Branches de trabalho
Cada alteração deve ser desenvolvida em uma branch específica, criada a partir da versão atualizada da `main`. As branches devem ter escopo bem definido e duração curta, evitando o acúmulo de alterações não relacionadas.
A nomenclatura deve seguir o formato `<tipo>/<descricao-curta>`, utilizando letras minúsculas e hífens para separar palavras. Os tipos previstos são:
- **`feature/`**: desenvolvimento de novas funcionalidades.
- **`fix/`**: correção de defeitos.
- **`hotfix/`**: correção urgente de problemas em produção.
- **`refactor/`**: reorganização do código sem alteração do comportamento esperado.
- **`docs/`**: criação ou atualização da documentação.
- **`chore/`**: tarefas de manutenção, como ajustes em ferramentas e dependências.
  Exemplos de nomes incluem `feature/autenticacao-usuarios`, `fix/validacao-cadastro` e `docs/instrucoes-instalacao`. Quando houver uma tarefa ou ocorrência associada, seu identificador pode ser incluído no nome da branch.
#### Integração de alterações
A integração deve ocorrer por meio de um _pull request_ que descreva o objetivo da alteração, as principais modificações e as validações realizadas. Antes da integração, o autor deve garantir que a branch esteja compatível com a `main`, resolver eventuais conflitos e obter a aprovação de pelo menos outro integrante da equipe.
As verificações automatizadas configuradas no projeto devem ser concluídas com sucesso. Após a integração, a branch de trabalho deve ser removida, mantendo o histórico da alteração acessível pelo _pull request_.
### Estratégia de backup e recuperação
#### Proteção do repositório
O repositório remoto no GitHub é a cópia central do projeto. Os integrantes devem manter suas alterações versionadas e integrá-las à branch principal por meio do fluxo de revisão definido na política de branching.
Sempre que uma versão estável for disponibilizada, deve ser criada uma tag correspondente, seguindo o padrão de versionamento semântico adotado pelo projeto. As tags facilitam a identificação e a recuperação de versões específicas.
#### Cópia adicional
Para reduzir a dependência de uma única plataforma, deve-se manter periodicamente uma cópia local atualizada do repositório ou um arquivo de backup que preserve o histórico do Git. A frequência deve ser compatível com o ritmo de alterações do projeto.
Credenciais, tokens e outras informações sensíveis não devem ser armazenados no repositório. Caso sejam expostos, devem ser revogados ou substituídos; remover o arquivo do histórico, por si só, não invalida uma credencial comprometida.
#### Recuperação
Em caso de exclusão ou indisponibilidade do repositório remoto, a recuperação pode ser feita a partir de uma cópia local atualizada, recriando o repositório remoto e enviando o histórico versionado. Para recuperar uma versão específica, devem ser utilizadas a tag correspondente e o commit associado.
Após a recuperação, deve-se verificar se os arquivos e o histórico esperado estão disponíveis e se a branch principal e as tags estão corretas. Como o projeto não possui banco de dados nem ambiente de deploy, a estratégia não contempla a restauração desses componentes.
#### Revisão
A equipe deve verificar periodicamente se há uma cópia adicional atualizada e se o procedimento de recuperação continua viável. A existência do repositório no GitHub, isoladamente, não substitui a manutenção de uma cópia independente.