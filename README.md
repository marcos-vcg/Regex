## REGEX - Guia de Metacaracteres
 Um guia resumido sobre os principais elementos de REGEX


## Representação

Meta | Nome | Função
--- | --- | ---
`.` | ponto | um caractere qualquer
`[]` | conjunto | conjunto de caracteres permitidos
`[^]` | conjunto negado | conjunto de caracteres proibidos
`\` | escape | uso de metacaracteres com literal
`|` | ou | operação ou
`()` | grupo | define um grupo
`\1...\9` | retrovisor | regata grupos ja definidos


## Quantificadores

Meta | Nome | Função
--- | --- | ---
`?` | opcional | zero ou um
`*` | asterisco | zero ou mais
`+` | mais | um ou mais
`{n, m}` | chaves | de n até m


##  Ancoras

Meta | Nome | Função
--- | --- | ---
`^` | circunflexo | inicio da linha
`$` | cifrao | fim da linha
`\b` | borda | inicio ou fim de palavra


## Shorthands

Meta | Função
--- | ---
`\A` | Corresponde somente ao início de uma sequência.
`\b` | Corresponde a um limite de palavras, isto é, a posição entre uma palavra e um espaço.
`\B` | Corresponde a um limite.
`\d` | Corresponde a um caractere de dígito.
`\D` | Corresponde a um caractere diferente de dígito.
`\f` | Corresponde a um caractere de alimentação de formulário.
`\n` | Corresponde a um caractere de nova linha.
`\r` | Corresponde a um caractere de retorno de linha.
`\s` | Corresponde a qualquer espaço em branco, incluindo espaços, tabulações, caracteres de alimentação de formulário, e assim por diante.
`\S` | Corresponde a qualquer caractere diferente de espaço em branco.
`\t` | Corresponde a um caractere de tabulação.
`\v` | Corresponde a um caractere de tabulação vertical.
`\w` | Corresponde a qualquer caractere de texto, incluindo sublinhado. Essa expressão é equivalente a [A-Za-z0-9_].
`\W` | Corresponde a qualquer caractere diferente de palavra. Essa expressão é equivalente a [^A-Za-z0-9_].
`\z` | Corresponde somente ao fim de uma sequência.
`\Z` | Corresponder somente ao fim de uma sequência ou antes de um caractere de nova linha no final.


## POSIX

Meta | ASCII |Função
--- | --- | ---
`[:alnum:]` | `[a-zA-Z0-9]` | caracteres alfanumericos
`[:alpha:]` | `[a-zA-Z]` | Caracteres alfabéticos
`[:ascii:]` | `[\x00-\x7F]` | Caracteres ASCII
`[:blank:]` | `[\s\t]` | espaço e tab
`[:cntrl:]` | `[\x00-\x1F\x7F]` | Caracteres de controle
`[:digit:]` | `[0-9]` | digitos
`[:graph:]` | `[\x21-\x7E]` | Caracteres visíveis (qualquer coisa, exceto espaços e caracteres de controle)
`[:lower:]` | `[a-z]` | Letras minúsculas
`[:print:]` | `[\x20-\x7E]` | Caracteres e espaços visíveis (qualquer coisa, exceto caracteres de controle)
`[:punct:]` | `[!"\#$%&'()*+,\-./:;<=>?@\[\\\]^_{|}~]` | Pontuação (e símbolos).
`[:space:]` | `[ \t\r\n\v\f]` | Todos os caracteres de espaço em branco, incluindo quebras de linha
`[:upper:]` | `[A-Z]` | Letras maiúsculas
`[:word:]` | `[A-Za-z0-9_]` | Caracteres do Word (letras, números e sublinhados)
`[:xdigit:]` | `[A-Fa-f0-9]` | Dígitos hexadecimais


## Links

[Os Metacaracteres](https://aurelio.net/regex/guia/metacaracteres.html)  
[Cheat sheet - Metacaracteres](http://www.devfuria.com.br/regex/cheat-sheet-matacaracteres/)
