# CI compartilhado

Workflow reutilizável para projetos Next.js com npm, `package-lock.json`, `npm run lint` e `npm run build` na raiz. Usa Node.js 24, executa lint e build com verificação de tipos e não publica aplicações.

## Adoção

Copie `workflow-templates/nextjs-ci.yml` para `.github/workflows/ci.yml` do projeto e substitua `$default-branch` pelo nome real da branch padrão. Abra um PR e confira o resultado no GitHub Actions antes de integrar.

O consumidor fixa o SHA do workflow reutilizável. Atualizações centrais só chegam aos projetos quando esse SHA é atualizado por um novo PR. As actions de checkout e Node também estão fixadas por SHA.

## Limites

- A conta é pessoal. Não se promete exibição automática deste template no catálogo Actions; o catálogo de templates organizacionais é documentado para organizações.
- Não aplicar em projetos sem Next.js, sem lockfile npm ou com comandos incompatíveis.
- O build deve funcionar sem credenciais de produção. Não há `secrets: inherit` nem credenciais de banco, e-mail ou deploy neste workflow.
- O token tem somente leitura de conteúdo. O checkout não persiste credenciais.
- Lint e build não substituem testes funcionais, de autorização ou das integrações.
- Os checks precisam ser aprovados antes de considerar regras de merge obrigatório; este repositório não configura essas regras.

## Referências

- [Workflow templates](https://docs.github.com/en/actions/how-tos/reuse-automations/create-workflow-templates)
- [Workflows reutilizáveis](https://docs.github.com/en/actions/concepts/workflows-and-actions/reusing-workflow-configurations)
