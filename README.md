Aqui você vai aprender como fazer a cobrinha que vai comendo conforme sua "movimentação" no git.

Passo-a-Passo
1- Crie um repositório com seu nome de usuario git

2- Abra o seu Readme.md e cole o seguinte svg e substitua - "SEU USER NAME GIT" - pelo seu nome de usuario:

    ![Snake animation](https://github.com/SEU USER NAME GIT/SEU USER NAME GIT/blob/output/github-contribution-grid-snake.svg)

3- Feito isso você deve agora criar uma GitHub Action. Para isso, siga os passos:
    1- Com seu repositório aberto vá até a aba Actions

    2- Em seguida clique na opção:
    set up a workflow yourself ->

    3- No arquivo que se abre, substitua todo código pelo seguinte:

        name: Generate Datas

        on:
            schedule: # execute every 12 hours
                - cron: "* */12 * * *"
            workflow_dispatch:

            jobs:
                build:
                    name: Jobs to update datas
                    runs-on: ubuntu-latest
                    steps:
                        # Snake Animation
                        - uses: Platane/snk@master
                        id: snake-gif
                        with:
                            github_user_name: SEU USER NAME
                            svg_out_path: dist/github-contribution-grid-snake.svg

                        - uses: crazy-max/ghaction-github-pages@v2.1.3
                        with:
                            target_branch: output
                            build_dir: dist
                        env:
                            GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

    4- Execute sua Action selecionando: View runs
        E em seguida: Run workflow

Atenção: Não é preciso rodar sua Action toda vez que fizer alguma ação no GitHub pois ela atualiza altomaticamente a cada 12 horas.


