Aqui está a tradução do README:

---

# Kit de Treinamento do GitHub

Material didático de código aberto da equipe de Serviços Profissionais do GitHub.

## Nós ❤️ colaboradores como você

**Estamos ansiosos para trabalhar com você**, nossa comunidade de usuários, para melhorar esses materiais e desenvolver novos. Confira nosso [guia de CONTRIBUIÇÃO](CONTRIBUTING.md) para mais informações sobre como começar.

## Procurando por um recurso que já esteve neste repositório?

Este repositório atualmente contém folhas de dicas de Git e GitHub. Se você está procurando por um projeto que já esteve aqui, como treinamentos sob demanda, listas de leitura, vídeos e recomendações de livros, veja [este commit](https://github.com/github/training-kit/tree/4fbf180e980ef973ba4cc4b8ef3d5f278ddc8c08) no histórico do repositório.

## Projetos usados no kit de treinamento

- Usamos [Jekyll](https://jekyllrb.com/) e [Markdown](https://guides.github.com/features/mastering-markdown/).
- Nosso conteúdo é estilizado usando o [toolkit CSS Primer](https://github.com/primer/primer-css).

## Empacotando para visualização interna

Se você quiser ter uma cópia dos arquivos para serem servidos de um servidor web interno, comece rodando `script/package`.

1. Execute `script/package` para criar um arquivo tar de lançamento. Ele estará no formato `release-XXXXXXX.tgz` para você levar aonde quiser.
2. Para testar se está tudo certo, crie algumas pastas `mkdir -p test_site/kit`.
3. Extraia o lançamento, `tar -xzf release-XXXXXXX.tgz -C test_site/kit`.
4. Acesse o diretório test_site, `cd test_site`.
5. Visualize o site:
    - Para a versão Python 2.x, execute: `python -m SimpleHTTPServer`
    - Para a versão Python 3.x, execute: `python -m http.server`
    - _Nota: Alguns servidores são mais avançados que outros e podem lidar com redirecionamentos, reconhecimento inteligente de arquivos `.html`, etc._

O conteúdo do site está licenciado sob a [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/). A licença CC-BY-4.0 permite que você use o conteúdo para quase qualquer propósito, mas não concede permissões de marca registrada, desde que você mencione a licença e dê crédito, como a seguir:

> Conteúdo baseado em [github.github.com/training-kit/](https://github.github.com/training-kit) usado sob a licença [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/).

O código usado para construir e testar o site, bem como exemplos de código no site, se houver, está licenciado sob [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/legalcode). A CC0 renuncia a todas as restrições de direitos autorais, mas não concede permissões de marca registrada.

Isso significa que você pode usar o conteúdo e código deste repositório, exceto pelas marcas registradas do GitHub, em seus projetos.

Quando você contribui para este repositório, você está fazendo isso sob as licenças mencionadas acima.

## FACCAT - Engenharia de Software
> Exercício 02 (para TED): Controle de versões com Git  
Grupo 01: Camila, Emily e Victor

---

Espero que a tradução ajude!