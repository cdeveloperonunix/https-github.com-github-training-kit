# O que é o Git?

Git é um [sistema de controle de versões](https://pt.wikipedia.org/wiki/Sistema_de_controle_de_vers%C3%B5es) distribuído, usado principalmente no [desenvolvimento de software](https://pt.wikipedia.org/wiki/Desenvolvimento_de_software), mas pode ser usado para registrar o histórico de edições de qualquer tipo de arquivo (Exemplo: alguns livros digitais são disponibilizados no [GitHub](https://pt.wikipedia.org/wiki/GitHub) e escrito aos poucos publicamente). O Git foi inicialmente projetado e desenvolvido por [Linus Torvalds](https://pt.wikipedia.org/wiki/Linus_Torvalds) para o desenvolvimento do [kernel Linux](https://pt.wikipedia.org/wiki/Linux_(n%C3%BAcleo)), mas foi adotado por muitos outros projetos.


# Boas práticas de versionamento com Git

- Commits pequenos e frequentes: Realize commits com frequência para evitar grandes mudanças de uma só vez. Isso facilita a reversão e o rastreamento de problemas.
- Mensagens claras de commit: Use mensagens de commit descritivas e significativas, indicando o que foi alterado e por quê. Evite termos genéricos como "ajustes" ou "corrigido".
- Branches para funcionalidades: Crie branches para novas funcionalidades, correções de bugs ou experimentos. Isso permite que o trabalho seja isolado da branch principal (geralmente "main" ou "master").
- Merges e pull requests: Ao finalizar o desenvolvimento de uma funcionalidade, faça merge com a branch principal usando um pull request. Isso permite revisão de código e colaboração antes de incorporar as mudanças.
- Rebase em vez de merge (quando apropriado): Rebase pode ser usado para manter um histórico mais limpo, pois evita a criação de commits de merge extras. Contudo, ele deve ser utilizado com cuidado em projetos colaborativos.
- Uso adequado de tags: Utilize tags para marcar versões específicas do projeto, como releases ou milestones importantes.
- Resolução de conflitos: Ao fazer merge de branches, pode haver conflitos de código. Resolva-os imediatamente e com cuidado, garantindo que o código final funcione corretamente.
- Uso de .gitignore: Configure o arquivo .gitignore para evitar que arquivos desnecessários (como arquivos temporários ou de build) sejam adicionados ao repositório.

---

# GitHub Training Kit

Open source courseware from the GitHub Professional Services team.

## We ❤️ contributors like you

**We’re eager to work with you**, our user community, to improve these materials and develop new ones. Please check out our [CONTRIBUTING guide](CONTRIBUTING.md) for more information on getting started.

## Looking for a resource that was once housed in training-kit?

This repository currently contains Git and GitHub cheat sheets. If you're looking for a project that used to be housed here, such as On-Demand training, reading lists, videos, and book recommendations, see [this commit](https://github.com/github/training-kit/tree/4fbf180e980ef973ba4cc4b8ef3d5f278ddc8c08) in the repository's history.

## Projects used in training-kit

- We use [Jekyll](https://jekyllrb.com/) and [Markdown](https://guides.github.com/features/mastering-markdown/).
- Our content is styled using the [Primer CSS toolkit](https://github.com/primer/primer-css).

## Packaging for viewing behind your firewall

If you'd like to have a copy of the files to be served from a web server inside your firewall, start by running `script/package`.

1. Run `script/package` to create a release tarball. This will be in the format `release-XXXXXXX.tgz` for you to take wherever you want.
2. To test this looks okay, create some folders `mkdir -p test_site/kit`.
3. Extract the release, `tar -xzf release-XXXXXXX.tgz -C test_site/kit`.
4. Switch into the test_site directory, `cd test_site`.
5. View the site:
    - For python version 2.x, run: `python -m SimpleHTTPServer`
    - For python version 3.x, run: `python -m http.server`
    - _Note: Some servers are more advanced than others and can handle redirects, smart recognition of `.html` files, etc_

Site content is licensed under [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/). CC-BY-4.0 gives you permission to use the content for almost any purpose but does not grant you any trademark permissions, so long as you note the license and give credit, such as follows:

> Content based on [github.github.com/training-kit/](https://github.github.com/training-kit) used under the [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/) license.

Code used to build and test the site as well as code samples on the site, if any, are licensed under [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/legalcode). CC0 waives all copyright restrictions but does not grant you any trademark permissions.

This means you can use the content and code in this repository except for GitHub trademarks in your projects.

When you contribute to this repository you are doing so under the above licenses.
