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




## Exemplos Práticos

## Número de telefone

```javascript
const text = `
- (77) 95684-9783
- 905731497
- 29233
`;
const regex = /(\((\d{2})\)\s?)?(\d{4,5})[-]?(\d{4})/gm;
console.log(text.match(regex));
// [ '(77) 95684-9783', '905731497' ]
```

## CEP

```javascript
const text = `
- 69.938-863
- 72874988
- 9235
`;
const regex = /(\d{2}[.]?\d{3})[-]?(\d{3})/gm;
console.log(text.match(regex));
// [ '69.938-863', '72874988' ]
```

## CPF

```javascript
const text = `
- 294.755.728-05
- 31568262353
- 92374
`;
const regex = /(\d{3})[.]?(\d{3})[.]?(\d{3})[-]?(\d{2})/gm;
console.log(text.match(regex));
// [ '294.755.728-05', '31568262353' ]
```

## CNPJ

```javascript
const text = `
- 97.164.674/0001-63
- 57783170000107
- 29384
`;
const regex = /(\d{2})[.]?(\d{3})[.]?(\d{3})[/]?(\d{4})[-]?(\d{2})/gm;
console.log(text.match(regex));
// [ '97.164.674/0001-63', '57783170000107' ]
```

## CPF e CNPJ ao mesmo tempo

```javascript
const text = `
- 294.755.728-05
- 97.164.674/0001-63
- 28574
`;
const regex = /((\d{2})[.]?(\d{3})[.]?(\d{3})[/]?(\d{4})[-]?(\d{2}))|((\d{3})[.]?(\d{3})[.]?(\d{3})[-]?(\d{2}))/gm;
console.log(text.match(regex));
// [ '294.755.728-05', '97.164.674/0001-63' ]
```

## Título de eleitor

```javascript
const text = `
- 9165.1348.1830
- 871560272755
- 39675
`;
const regex = /(\d{4})[.]?(\d{4})[.]?(\d{4})/gm;
console.log(text.match(regex));
// [ '9165.1348.1830', '871560272755' ]
```

## PIS/PASEP

```javascript
const text = `
- 038.54391.67-8
- 8972716250-2
- 74189
`;
const regex = /(\d{3})[.]?(\d{5})[.]?(\d{2})[-]?(\d)/gm;
console.log(text.match(regex));
// [ '038.54391.67-8', '8972716250-2' ]
```

## CNH

```javascript
const text = `
- 151464680-66
- 19533844800
- 23741
`;
const regex = /(\d{9})[-]?(\d{2})/gm;
console.log(text.match(regex));
// [ '151464680-66', '19533844800' ]
```

## Placa de carros no padrão normal e o novo padrão Mercosul

```javascript
const text = `
- RKN-4503
- MOD3L05
- TEST
`;
const regex = /(([A-Z]{3})[-]?(\d{4}))|(([A-Z]{3})(\d{1})([A-Z]{1})(\d{2}))/gm;
console.log(text.match(regex));
// [  'RKN-4503', 'MOD3L05' ]
```

## Renavam

```javascript
const text = `
- 2406618318-6
- 30693589258
- 38493
`;
const regex = /(\d{10})[-]?(\d{1})/gm;
console.log(text.match(regex));
// [ '2406618318-6', '30693589258' ]
```

## Inscrição Estadual

```javascript
const text = `
- AC - 01.618.974/339-10
- AL - 2480456110
- AP - 039519660
- AM - 80.938.148-6
- BA - 116884-93
- CE - 53525140-8
- DF - 07127383001-42
- ES - 46249822-0
- GO - 10.945.363-8
- MA - 12749382-4
- MT - 7901625213-0
- MS - 28825429-5
- MG - 087.075.583/0925
- PA - 15-919530-6
- PB - 41867640-2
- PR - 042.31026-32
- PE - 4956703-91
- PI - 80788482-0
- RJ - 89.048.76-1
- RN - 20.210.143-6
- RS - 993/7064762
- RO - 2860516573540-8
- RR - 24259146-1
- SP - 365.456.289.105
- SC - 975.869.620
- SE - 22610269-6
- TO - 9703391962-0
`;
const regex = /(?=\d)(?![\d/\-.]*[/\-.]{2})[\d/\-.]{1,16}\d/gm;
console.log(text.match(regex));
/*
[ 
  '01.618.974/339-10',
  '2480456110',
  '039519660',
  '80.938.148-6',
  '116884-93',
  '53525140-8',
  '07127383001-42',
  '46249822-0',
  '10.945.363-8',
  '12749382-4',
  '7901625213-0',
  '28825429-5',
  '087.075.583/0925',
  '15-919530-6',
  '41867640-2',
  '042.31026-32',
  '4956703-91',
  '80788482-0',
  '89.048.76-1',
  '20.210.143-6',
  '993/7064762',
  '2860516573540-8',
  '24259146-1',
  '365.456.289.105',
  '975.869.620',
  '22610269-6',
  '9703391962-0'
]
*/
```

## Cartão Mastercard

```javascript
const text = `
- 5125 8108 3239 3913
- 5213-4033-9663-4675
- 5460805328094911
- 557107
`;
const regex = /(?=[5][1-5])(\d{4})[\s-.]?(\d{4})[\s-.]?(\d{4})[\s-.]?(\d{4})/gm;
console.log(text.match(regex));
// [ '5125 8108 3239 3913', '5213-4033-9663-4675', '5460805328094911' ]
```

## Cartão Visa

```javascript
const text = `
- 4929 8066 6172 1969
- 4024.0071.9067.6451
- 4556201055723856
- 23455
`;
const regex = /(?=[4])(\d{4})[\s-.]?(\d{4})[\s-.]?(\d{4})[\s-.]?(\d{4})/gm;
console.log(text.match(regex));
// [ '4929 8066 6172 1969', '4024.0071.9067.6451', '4556201055723856' ]
```

## CVV dos cartões Mastercard ou Visa

```javascript
const text = `
- 894
- 81
`;
const regex = /(\d{3})/gm;
console.log(text.match(regex));
// [ '894' ]
```

## Validade dos cartões Mastercard ou Visa

```javascript
const text = `
- 06/20
- 03-21
- 0425
- 34
`;
const regex = /(?=(0[1-9])|(1[0-2]))([0-1][0-9])[/-]?(\d\d)/gm;
console.log(text.match(regex));
// [ '06/20', '03-21', '0425' ]
```

## Validação de senha forte

Para validar precisa:
- Pelo menos uma letra maiúscula;
- Pelo menos um número;
- Pelo menos um simbolo `(!@#$%&*()-+.,;?{[}]^><:)`;
- Que tenha entre 6 a 12 caracteres;
- Aceitando somente letras de `a - z` maiúscula e minúscula, números e os simbolos `(!@#$%&*()-+.,;?{[}]^><:)`

> O método `test` do objeto `RegExp`, testa se a string contem ou não nossa regra.
```javascript
const senha1 = 'mm7i%KX^+';
const senha2 = 'y-fw6&q';
const senha3 = 'kA{Lbo';
const senha4 = 'uuksEy6';
const senha5 = '(8gp30d0@%;Ms}0';
const senha6 = 'U:oTKrçãé';
const regex = /^(?=.*[A-Z])(?=.*\d)(?=.*[!@#$%&*()+\-.,;?\^.,;?><:{}\[\]])[\w!@#$%&*()+\-.,;?\^.,;?><:{}\[\]]{6,12}$/;
console.log(regex.test(senha1)); //true
console.log(regex.test(senha2)); //false (não contem uma letra maiúscula)
console.log(regex.test(senha3)); //false (não contem pelo menos um número)
console.log(regex.test(senha4)); //false (não contem pelo menos um simbolo)
console.log(regex.test(senha5)); //false (contem mais de 12 caracteres)
console.log(regex.test(senha6)); //false (contem caracteres diferentes de letras de a-z, números ou simbolo)
```

## Validação de email

```javascript
const email1 = 'kpastornilson.i@worthwre.com';
const email2 = 'fsimo.test.12q@6686088-.com';
const regex = /^(\S+)@((?:(?:(?!-)[a-zA-Z0-9-]{1,62}[a-zA-Z0-9])\.)+[a-zA-Z0-9]{2,12})$/;
console.log(regex.test(email1)); //true
console.log(regex.test(email2)); //false
```
> Todos emails foram gerados usando o site [generator.email](https://generator.email/)

## Validação de datas

Regras para validar:
- Se o ano é bissexto;
- Se o mês pode ou não ter 31 dias;
- Aceita os separadores `[\/\-.]`;
- Dia e mês podem vir somente com um dígito;
- Podemos ter a representação de ano, com 2 ou 4 dígitos;

```javascript
const data1 = '29/02/52';
const data2 = '31/7/1998';
const data3 = '32/09/1998';
const regex = /^((?:(?=29[\/\-.]0?2[\/\-.](?:[1-9]\d)?(?:[02468][048]|[13579][26])(?!\d))29)|(?:(?=31[\/\-.](?!11)0?[13578]|1[02])31)|(?:(?=\d?\d[\/\-.]\d?\d[\/\-.])(?!29[\/\-.]0?2)(?!31)(?:[12][0-9]|30|0?[1-9])))[\/\-.](0?[1-9]|1[0-2])[\/\-.]((?:[1-9]\d)?\d{2})$/;
console.log(regex.test(data1)); //true
console.log(regex.test(data2)); //true
console.log(regex.test(data3)); //false
```
> Tem varios testes no site [regex101](https://regex101.com/r/f9avRz/12).



## Links

[Os Metacaracteres](https://aurelio.net/regex/guia/metacaracteres.html)  
[Cheat sheet - Metacaracteres](http://www.devfuria.com.br/regex/cheat-sheet-matacaracteres/)
[4Devs](https://www.4devs.com.br/)  
[Gerador Brasileiro](http://geradorbrasileiro.com/)  
[O que significa cada número do cartão de crédito](https://www.tecmundo.com.br/cartao-de-credito/43322-o-que-significa-cada-numero-do-cartao-de-credito-ilustracao-.htm)