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


