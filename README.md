<a name="logo"/>
<div align="center">
<a href="https://julialang.org/" target="_blank">
<img src="doc/src/assets/logo.svg" alt="Julia Logo" width="210" height="142"></img>
</a>
</div>

<table>
    <!-- Docs -->
    <tr>
        <td>Documentation</td>
        <td>
            <a href="https://docs.julialang.org"><img src='https://img.shields.io/badge/docs-v1-blue.svg'/></a>
        </td>
    </tr>
    <!-- Continuous integration
    To change the badge to point to a different pipeline, it is not sufficient to simply change the `?branch=` part.
    You need to go to the Buildkite website and get the SVG URL for the correct pipeline. -->
    <tr>
        <td>Continuous integration</td>
        <td>
            <a href="https://buildkite.com/julialang/julia-master"><img src='https://badge.buildkite.com/f28e0d28b345f9fad5856ce6a8d64fffc7c70df8f4f2685cd8.svg?branch=master'/></a>
        </td>
    </tr>
    <!-- Coverage -->
    <tr>
        <td>Code coverage</td>
        <td>
            <a href="https://coveralls.io/r/JuliaLang/julia?branch=master"><img src='https://img.shields.io/coveralls/github/JuliaLang/julia/master.svg?label=coveralls'/></a> <a href="https://codecov.io/github/JuliaLang/julia?branch=master"><img src='https://img.shields.io/codecov/c/github/JuliaLang/julia/master.svg?label=codecov'/></a>
        </td>
    </tr>
</table>

## A Linguagem Julia

Julia é uma linguagem dinâmica de alto nível e alto desempenho para
Informática. A página principal de Julia pode ser encontrada em
[julialang.org](https://julialang.org/). Este é o GitHub
repositório do código-fonte Julia, incluindo instruções para compilar
e instalando Julia, abaixo.

## Resources

- **Homepage:** <https://julialang.org>
- **Binários:** <https://julialang.org/downloads/>
- **Código fonte:** <https://github.com/JuliaLang/julia>
- **Documentação:** <https://docs.julialang.org>
- **Pacotes:** <https://julialang.org/packages/>
- **Fórum de discussão:** <https://discourse.julialang.org>
- **Slack:** <https://julialang.slack.com> (get an invite from <https://julialang.org/slack/>)
- **YouTube:** <https://www.youtube.com/user/JuliaLanguage>
- **Cobertura do código:** <https://coveralls.io/r/JuliaLang/julia>

Novos desenvolvedores podem encontrar as notas em
[CONTRIBUINDO](https://github.com/JuliaLang/julia/blob/master/CONTRIBUTING.md)
útil para começar a contribuir para a base de código Julia.

### Recursos Externos

- [**StackOverflow**](https://stackoverflow.com/questions/tagged/julia-lang)
- [**Twitter**](https://twitter.com/JuliaLanguage)
- [**Learning resources**](https://julialang.org/learning/)

## Instalação do Binário

Se você preferir não compilar a última Julia da fonte,
tarballs específicos da plataforma com binários pré-compilados também são
[disponível para download](https://julialang.org/downloads/). o
página de downloads também fornece detalhes sobre o
[diferentes níveis de suporte](https://julialang.org/downloads/#supported_platforms)
para combinações de SO e plataforma.

Se tudo funcionar corretamente, você verá um banner Julia e um
prompt interativo no qual você pode inserir expressões para
avaliação. Você pode ler sobre [obter
iniciado](https://docs.julialang.org/en/v1/manual/getting-started/) no manual.

**Observação**: Embora alguns gerenciadores de pacotes do sistema forneçam Julia, como
instalações não são mantidas nem endossadas pela Julia
projeto. Eles podem estar desatualizados, quebrados e/ou sem manutenção. Nós
recomendo que você use os binários oficiais do Julia.

## Construindo Julia

Primeiro, certifique-se de ter todos os [requeridos
dependências](https://github.com/JuliaLang/julia/blob/master/doc/src/devdocs/build/build.md#required-build-tools-and-external-libraries) instalado.
Em seguida, adquira o código-fonte clonando o repositório git:

    git clone https://github.com/JuliaLang/julia.git

e, em seguida, use o prompt de comando para mudar para o diretório julia resultante. Por padrão, você estará compilando a versão instável mais recente do
Júlia. No entanto, a maioria dos usuários deve usar a [versão estável mais recente](https://github.com/JuliaLang/julia/releases)
de Júlia. Você pode obter esta versão executando:

    git checkout v1.8.2
    
Para construir o executável `julia`, execute `make` a partir do diretório julia.

Construir Julia requer 2 GiB de espaço em disco e aproximadamente 4 GiB de memória virtual.

**Nota:** O processo de compilação falhará muito se algum dos diretórios pai do diretório de compilação tiver espaços ou outros meta-caracteres do shell, como `$` ou `:` em seus nomes (isto é devido a uma limitação no GNU make ).

Uma vez construído, você pode executar o executável `julia`. De dentro do diretório julia, execute

    ./julia

Seu primeiro teste de Julia determina se sua compilação está funcionando
devidamente. Da julia
diretório, digite `make testall`. Você deve ver a saída que
lista uma série de testes em execução; se eles completarem sem erros, você
deve estar em boa forma para começar a usar Julia.

Você pode ler sobre [obter
iniciado](https://docs.julialang.org/en/v1/manual/getting-started/)
no manual.

Instruções detalhadas de construção, caso sejam necessárias,
estão incluídos na [documentação de compilação](https://github.com/JuliaLang/julia/blob/master/doc/src/devdocs/build/).

### Desinstalando Julia

Por padrão, Julia não instala nada fora do diretório que foi clonado
em e `~/.julia`. Julia e a grande maioria dos pacotes Julia podem ser
completamente desinstalado excluindo esses dois diretórios.

## Organização do código-fonte

O código fonte de Julia está organizado da seguinte forma:
| Diretório         | Conteúdo                                                              |
| -                 | -                                                                     |
| `base/`           | código-fonte para o módulo Base (parte da biblioteca padrão de Julia) |
| `stdlib/`         | código-fonte para outros pacotes de biblioteca padrão                 |
| `cli/`            | fonte para a interface de linha de comando/REPL                       |
| `contrib/`        | roteiros diversos                                                     |
| `deps/`           | dependências externas                                                 |
| `doc/src/`        | fonte para o manual do usuário                                        |
| `src/`            | fonte para o núcleo da linguagem Julia                                |
| `teste/`          | suítes de teste                                                       |
| `usr/`            | binários e bibliotecas compartilhadas carregadas pelas bibliotecas    |  
|                   | padrão de Julia                                                       |

## Terminal, Editores e IDEs

O Julia REPL é bastante poderoso. Consulte a seção do manual sobre
[a Julia REPL](https://docs.julialang.org/en/v1/stdlib/REPL/)
para mais detalhes.

No Windows, recomendamos executar Julia em um terminal moderno,
como [Windows Terminal da Microsoft Store](https://aka.ms/terminal).

Suporte para edição de Julia está disponível para muitos
[editores amplamente usados](https://github.com/JuliaEditorSupport):
[Emacs](https://github.com/JuliaEditorSupport/julia-emacs),
[Vim](https://github.com/JuliaEditorSupport/julia-vim),
[Sublime Text](https://github.com/JuliaEditorSupport/Julia-sublime) e muitos
outros.
Para usuários que preferem IDEs, recomendamos usar o VS Code com o
[julia-vscode](https://www.julia-vscode.org/) plugin.
Para usuários de notebooks, o suporte a notebooks [Jupyter](https://jupyter.org/) está disponível por meio do
pacote [IJulia](https://github.com/JuliaLang/IJulia.jl) e
o pacote [Pluto.jl](https://github.com/fonsp/Pluto.jl) fornece notebooks Pluto.
