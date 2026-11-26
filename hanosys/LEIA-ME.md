# HanoSys Suporte (RustDesk personalizado)

Programa de suporte remoto da HanoSys Tecnologia, baseado no [RustDesk](https://github.com/rustdesk/rustdesk)
(AGPL-3.0). Este repositório é uma cópia pública do RustDesk com as mudanças da HanoSys, como pede a licença.

## O que muda em relação ao RustDesk 1.5.3
- `src/common.rs`: chave pública que confere o `custom.txt` (a da HanoSys, no lugar da do gerador do RustDesk Pro).
- `hanosys/custom.txt`: configuração assinada — nome "HanoSys", servidor `acesso.hanosys.com.br` e a chave dele, idioma pt-BR.
- Ícones (`res/`, `flutter/windows/runner/resources/app_icon.ico`) e logos (`flutter/assets/icon.*`, `logo*.png`).
- `flutter/windows/runner/Runner.rc`: empresa e nome do produto.
- `.github/workflows/hanosys-windows.yml`: montagem só do Windows x64; os outros workflows foram tirados desta branch.

## Como gerar uma versão
Criar e enviar uma tag `hanosys-<versão>-<n>` (ex.: `hanosys-1.5.3-1`). O GitHub monta e publica em Releases o
`hanosys-suporte-<versão>.exe` (portátil: abre sem instalar e tem a opção de instalar).

## Montagens
- 1.5.3-4: atualização automática bloqueada.
- 1.5.3-5: senha permanente padrão dos clientes (hash no custom.txt).
- 1.5.3-6/7: servidor de API próprio (https://acesso.hanosys.com.br) para sinal de vida, dados do computador e sessões.
- 1.5.3-8: conecta com o programa logado (o hbbs livre não faz a troca de chaves; antes dava "Failed to secure tcp: deadline has elapsed"); o token do login não vai ao hbbs.
