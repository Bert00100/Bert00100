# Manutenção do perfil

O README usa Markdown e HTML aceitos pelo GitHub, com um cabeçalho SVG local e cards versionados. Os links dos projetos foram conferidos na API pública do GitHub.

## Conteúdo profissional

Atualização editorial: 27/09/2026. Fontes: currículo local em `/home/user/code/Curriculo/index.html`, perfil público do [LinkedIn](https://www.linkedin.com/in/felipefranceschini/) e repositórios de [Bert00100](https://github.com/Bert00100).

O currículo fundamenta as tecnologias, os projetos e os resultados de 40 → 20 minutos e 5 → 2 minutos. Esses resultados são relatos profissionais do currículo, não medições deste repositório.

Há uma divergência: o currículo apresenta a Mettric como vínculo atual, mas a parte pública do LinkedIn exibe uma publicação de despedida. O README descreve a experiência sem afirmar emprego atual. A conclusão de ADS em 2025 segue o currículo; a emissão de certificado em 2026 no LinkedIn não foi interpretada como uma nova data de conclusão.

## Atualização dos cards

O endpoint anterior, `github-readme-stats.vercel.app`, retornou `DEPLOYMENT_PAUSED` durante a revisão. A solução usa a [GitHub Readme Stats Action](https://github.com/stats-organization/github-readme-stats-action) para gerar SVGs no próprio repositório, sem depender desse endpoint na visualização.

- Workflow: `profile-stats.yml`, diariamente às 09:23 UTC (06:23 em São Paulo), manualmente ou quando o README/workflow é alterado na `main`.
- A publicação dos arquivos na `main` dispara a primeira execução. Também é possível acessar **Actions → Atualizar cards do perfil → Run workflow**.
- Usa o `GITHUB_TOKEN` automático, com `contents: write` para salvar os dois SVGs. Não exige cadastrar um token pessoal.
- A Action está fixada por commit e a biblioteca em `2.2.1`.
- `fail_on_error: true` impede que um erro da API substitua as últimas imagens válidas. Ambos os cards precisam ser gerados antes de qualquer commit.
- Os commits do bot não disparam uma nova execução; os caminhos dos cards também estão fora do filtro de `push`.

Se a gravação falhar, confira o log do workflow, as permissões de Actions e eventuais regras de proteção da `main`. O agendamento depende de Actions habilitado e do workflow na branch padrão; o GitHub pode atrasar execuções e desabilitar agendamentos em repositórios públicos após 60 dias sem atividade. Veja a [documentação de agendamento](https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#schedule).

## Como interpretar

Os cards mostram estatísticas públicas. Commits usam o ano corrente (`include_all_commits=false` e `commits_year` calculado em UTC a cada execução); os demais indicadores seguem as definições da biblioteca. Linguagens refletem o tamanho do código nos repositórios analisados, não proficiência nem tempo de trabalho. Commits em GitLab não entram nas estatísticas do GitHub.

Contribuições privadas e commits que não atendam aos critérios de atribuição do GitHub podem não aparecer. O README não promete contá-los. Consulte os [critérios de contribuições do GitHub](https://docs.github.com/en/account-and-profile/how-tos/contribution-settings/troubleshooting-missing-contributions).

O cabeçalho está em `assets/header.svg`. O texto principal, os links e os projetos podem ser editados diretamente em `README.md`.

Os SVGs iniciais foram obtidos em 27/09/2026 na instância pública do [GitHub Stats Extended](https://github-stats-extended.vercel.app), com as mesmas opções visuais e período do workflow. As atualizações seguintes são geradas pela Action. Nenhum token pessoal foi usado para coletar esses números.
