# SASS: O CSS com superpoderes

COMANDO PARA COMPILAR O ARQUIVO SCSS PARA O ARQUIVO CSS

-> sass style.scss:style.css

PARA COMPILAR A CADA NOVA ALTERAÇÃO DEVEMOS UTILIZAR O COMANDO

-> sass --watch style.scss:style.css

CASO OS ARQUIVOS ESTEJAM EM PASTAS DIFERENTES...

-> sass --watch pasta1/style.scss:pasta2/style.css

SOMENTE COMENTÁRIOS MULTILINHA SÃO COMPILADOS PARA O ARQUIVO style.css

/* Este comentário aparecerá no arquivo style.css*/

// Este comentário somente aparecerá no arquivo style.scss

DIFERENÇA DE USO DOS ARQUIVOS SCSS X SASS (AMBAS AS EXTENSÕES PODEM SER USADAS)

-> style.scss
    body{
        text-align: center;
    }
-> style.sass
    body
        text-align:center

VARIÁVEIS SASS

-> $cordefundo: #ababcf;
-> $fonte-da-caixa: 1.5rem;

NESTING - ANINHAMENTO DE ESTILOS DE ELEMENTOS DESCENDENTES DENTRO DOS ESTILOS DOS ELEMENTOS PAI

-> Usando o padrão BEM e ...
-> Exemplo de Html:
<div class="classedopai">
    <p class="classedopai__filho">Um texto qualquer...</p>
</div>
-> Usando nesting no arquivo .scss:
.classedopai{
    //estilos do pai

    &__filho{
        //estilos do filho
    }
}

OBS: & é chamado parent selector. 

PLACEHOLDER SELECTOR

-> Declaração no início do arquivo:
%no-decoration{text-decoration: none;}
%u-decoration{text-decoration: underline;}

-> Uso

.link{
    @extend %no-decoration;
    &:hover{
        @extend %u-decoration;
    }
}

MIXIN - PERMITE A PADRONIZAÇÃO DE ESTILOS QUE SERÃO REUTILIZADOS

-> Declaração no inicio do arquivo:

@mixin nome_do_mixin1($variavel1, $variavel2,...) { //Podem ou não ter parâmetros
    propriedade1: valor;
    propriedade2: valor;
    propriedaden: valor;
    #{$variavel1}: $variavel2; 
}

@mixin nome_do_mixin2{
    @media screen and (min-width: 1000px){@content;}
}


-> Uso:
.classe{
    @include nome_do_mixin1(valor1,valor2);
    
    text-align: center;

    @include nome_do_mixin2{
        width: 75%;
    }
}

IMPORTAÇÃO DE SASS DE OUTRO ARQUIVO

-> Deve-se nomear os arquivos começamdo com underline, "_", (p.ex: _conteudo.scss, _rodape.scss, _barra-lateral)
-> Onde o arquivo for importado deverá ser colocada a declaração:
-> @import "conteudo"

-> Caso haja mais de um arquivo a ser importado...:
-> @import "conteudo", "rodapé", "barra-lateral", ...

FUNÇÕES

-> Exemplo

@function nomeFunc($param1, $param2,...){
    $soma = $param1 + $param2 + ...
    @return $soma
}

OUTRAS PROPRIEDADES

@use: carrega mixins, functions e variáveis de outras folhas de estilos Sass e combina o CSS de diversas folhas de estilo juntos.

@forward: carrega uma folha de estilo Sass e torna os mixins, functions e variáveis disponíveis quando a folha de estilo é carregada pela regra do @use.

@import: estende as regras de CSS para carregar styles, mixins, functions e variáveis de outras folhas de estilo.

@mixins e @include: facilitam a reutilização de trechos de código.

@function: define funções customizadas que podem ser utilizadas em expressões.

@extend: permite que os seletores herdem estilos uns dos outros.

@at-root: coloca estilos dentro dele na raiz do documento CSS.

@error: faz com que a compilação falhe com uma mensagem de erro.

@warn: imprime um aviso sem parar totalmente a compilação.

@debug: imprime uma mensagem para fins de debugging.

E também fluxos de controle, como: @if, @each, @for e @while.

