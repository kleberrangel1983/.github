# CI compartilhado

Workflows reutilizáveis para projetos Next.js e Node/estáticos com `package-lock.json`. O workflow Next.js usa Node.js 24, executa lint e build com verificação de tipos; o workflow Node/estático usa Node.js 22 e executa lint, testes e build quando os scripts existem. Nenhum publica aplicações.

## Adoção

Copie `workflow-templates/nextjs-ci.yml` ou `workflow-templates/node-static-ci.yml` para `.github/workflows/ci.yml` do projeto e substitua `$default-branch` pelo nome real da branch padrão. Abra um PR e confira o resultado no GitHub Actions antes de integrar.

O consumidor fixa o SHA do workflow reutilizável. Atualizações centrais só chegam aos projetos quando esse SHA é atualizado por um novo PR. As actions de checkout e Node também estão fixadas por SHA.

## Limites

- A conta é pessoal. Não se promete exibição automática deste template no catálogo Actions; o catálogo de templates organizacionais é documentado para organizações.
- Não aplicar em projetos sem o lockfile npm ou com comandos incompatíveis. O template Node/estático não substitui revisão de deploy de sites Vite/HTML.
- O build deve funcionar sem credenciais de produção. Não há `secrets: inherit` nem credenciais de banco, e-mail ou deploy neste workflow.
- O token tem somente leitura de conteúdo. O checkout não persiste credenciais.
- Lint e build não substituem testes funcionais, de autorização ou das integrações.
- Os checks precisam ser aprovados antes de considerar regras de merge obrigatório; este repositório não configura essas regras.

## Referências

- [Workflow templates](https://docs.github.com/en/actions/how-tos/reuse-automations/create-workflow-templates)
- [Workflows reutilizáveis](https://docs.github.com/en/actions/concepts/workflows-and-actions/reusing-workflow-configurations)
