# logger

Logger estruturado sobre `go.uber.org/zap`, usado pelo `fepb-email`.

## Procedência — leia antes de mudar qualquer coisa

Este repositório é uma **republicação**, não o histórico original.

O módulo era publicado como `go.fepb.org.br/logger`, um caminho de *vanity
import* servido por um site de GitHub Pages que deixou de existir. Em
2026-08-29 a situação era:

- `https://go.fepb.org.br/logger?go-get=1` devolvia 404, e por isso o
  `proxy.golang.org` também devolvia 404 — o módulo estava irresolvível de
  qualquer lugar, e todo CI do `fepb-email` quebrava em `go mod tidy`;
- o repositório `victorximenis/logger` existe, mas é **outro projeto**: módulo
  `github.com/victorximenis/logger`, outra estrutura (`adapters/`, `core/`),
  e sem a tag `v1.0.1`;
- a única cópia sobrevivente da `v1.0.1` estava num cache local de módulos Go.

O conteúdo aqui veio desse cache, e é íntegro: o hash do zip bate com a entrada
`go.fepb.org.br/logger v1.0.1 h1:zMtFiwDv6WKnzXR7OFf2g/EJPoqnuDltTqpia2GVhsQ=`
do `go.sum` do `fepb-email`, e `go mod verify` offline devolveu
`all modules verified`.

O que **não** foi preservado: o histórico de commits e a autoria original. Isto
é um artefato republicado, não um `git clone` do que existia.

## Por que o caminho do módulo mudou

De `go.fepb.org.br/logger` para `github.com/FEPB/logger`. Um domínio de vanity
import precisa ser publicamente legível por construção — o comando `go` faz a
requisição `?go-get=1` sem credencial. Como este repositório é privado e o CI já
resolve dependências privadas por `GOPRIVATE=github.com/FEPB/*` mais token, o
caminho direto do GitHub dispensa a indireção e a exposição pública que ela
exigia.
