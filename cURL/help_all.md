# Opções de Linha de Comando `curl` Formatadas

## Autenticação
- `--anyauth`  
  Selecionar qualquer método de autenticação

- `--aws-sigv4 <provider>`  
  Autenticação de assinatura AWS V4

- `--basic`  
  Autenticação HTTP Básica

- `--digest`  
  Autenticação HTTP Digest

- `--negotiate`  
  Usa autenticação HTTP Negotiate (SPNEGO)

- `--proxy-anyauth`  
  Qualquer método de autenticação de proxy

- `--proxy-basic`  
  Autenticação básica no proxy

- `--proxy-digest`  
  Autenticação Digest com o proxy

- `--proxy-negotiate`  
  Autenticação SPNEGO com o proxy

- `--proxy-ntlm`  
  Autenticação NTLM com o proxy

- `--sasl-authzid <identidade>`  
  Identidade para autenticação SASL

- `--sasl-ir`  
  Resposta inicial SASL

- `--krb <nível>`  
  Habilita Kerberos com segurança

- `-u, --user <usuário:senha>`  
  Usuário e senha do servidor

- `-U, --proxy-user <usuário:senha>`  
  Usuário e senha do proxy

## Certificados e TLS
- `--ca-native`  
  Carrega certificados CA do sistema

- `--cacert <arquivo>`  
  Certificado CA para verificar o peer

- `--capath <dir>`  
  Diretório CA para verificar o peer

- `-E, --cert <arquivo[:senha]>`  
  Certificado de cliente e senha

- `--cert-type <tipo>`  
  Tipo de certificado (DER/PEM/ENG/P12)

- `--cert-status`  
  Verificar status OCSP do servidor

- `--ciphers <lista>`  
  Cifras TLS para usar

- `--curves <lista>`  
  Algoritmos EC para TLS

- `--crlfile <arquivo>`  
  Lista de revogação de certificados

- `--key <arquivo>`  
  Chave privada

- `--key-type <tipo>`  
  Tipo de chave privada (DER/PEM/ENG)

- `--pinnedpubkey <hashes>`  
  Chave pública fixa para verificar peer

- `--ssl`, `--ssl-reqd`  
  Habilita TLS / Exige TLS

- `--ssl-allow-beast`, `--ssl-no-revoke`, `--ssl-revoke-best-effort`, `--ssl-auto-client-cert`  
  Opções para SSL avançado

- `--tls-max <VERSÃO>`  
  TLS versão máxima permitida

- `--tls13-ciphers <lista>`  
  Conjuntos de cifras TLS 1.3

- `--tlsauthtype`, `--tlspassword`, `--tlsuser`  
  Configurações TLS adicionais

- `-2`, `--sslv2` / `-3`, `--sslv3` / `--tlsv1.x`  
  Força versões específicas de TLS

## Conexão e Rede
- `--connect-timeout <s>`  
  Tempo máx. para conectar

- `--connect-to <HOST1:PORT1:HOST2:PORT2>`  
  Redireciona conexão

- `--interface <nome>`  
  Interface de rede a usar

- `--dns-interface`, `--dns-ipv4-addr`, `--dns-ipv6-addr`, `--dns-servers`  
  DNS personalizado

- `--happy-eyeballs-timeout-ms <ms>`  
  Atraso antes de tentar IPv4

- `-4`, `--ipv4` / `-6`, `--ipv6`  
  Forçar IPv4 ou IPv6

- `--local-port <intervalo>`  
  Porta local usada

- `--rate <velocidade>`  
  Taxa máxima de requisição

- `--tcp-fastopen`, `--tcp-nodelay`  
  Configurações TCP

## Cookies
- `-b, --cookie <dados|arquivo>`  
  Envia cookies

- `-c, --cookie-jar <arquivo>`  
  Salva cookies após operação

- `-j, --junk-session-cookies`  
  Ignora cookies de sessão

## Redirecionamento
- `-L, --location`  
  Seguir redirecionamentos

- `--location-trusted`  
  Envia credenciais com redirecionamento

- `--max-redirs <num>`  
  Máximo de redirecionamentos

- `--post301`, `--post302`, `--post303`  
  Mantém POST após redirecionamentos

## Proxy
- `-x, --proxy [proto://]host[:port]`  
  Define proxy

- `--proxy-cert <cert[:senha]>`, `--proxy-key`, `--proxy-cacert`, `--proxy-crlfile`  
  Certificados e segurança do proxy

- `--proxy-insecure`  
  Ignora verificação TLS do proxy

- `--proxytunnel`  
  Túnel HTTP com CONNECT

- `--proxy1.0 <host[:port]>`  
  Proxy HTTP/1.0

## Download/Upload
- `-o, --output <arquivo>`  
  Salva em arquivo

- `-O, --remote-name`  
  Usa nome do arquivo remoto

- `-T, --upload-file <arquivo>`  
  Envia arquivo

- `-C, --continue-at <offset>`  
  Retoma download

- `--create-dirs`  
  Cria diretórios locais necessários

- `--create-file-mode <modo>`  
  Define modo para arquivos criados

- `--limit-rate <velocidade>`  
  Limita velocidade

## Método de Requisição
- `-d, --data <dados>`  
  Envia dados POST

- `--data-ascii`, `--data-binary`, `--data-urlencode`, `--data-raw`  
  Variações de envio de dados

- `-F, --form <campo=conteúdo>`  
  Envia formulário MIME

- `--form-string`, `--form-escape`  
  Opções adicionais de formulário

- `-G, --get`  
  Transforma POST em GET

- `-X, --request <método>`  
  Define método HTTP

## Cabeçalhos
- `-H, --header <cabeçalho>`  
  Envia cabeçalho customizado

- `--proxy-header <cabeçalho>`  
  Cabeçalho para proxy

- `-e, --referer <URL>`  
  Define cabeçalho Referer

- `-A, --user-agent <nome>`  
  Define User-Agent

## Logs e Debug
- `-v, --verbose`  
  Modo detalhado

- `-s, --silent`  
  Modo silencioso

- `-S, --show-error`  
  Mostra erro em modo `-s`

- `--trace <arquivo>`, `--trace-ascii`, `--trace-time`, `--trace-ids`, `--trace-config`  
  Opções de rastreio

- `--styled-output`  
  Saída estilizada

- `--stderr <arquivo>`  
  Redireciona stderr

## Tempo e Condições
- `-m, --max-time <s>`  
  Tempo máx. da transferência

- `--retry <num>`  
  Número de tentativas

- `--retry-delay <s>`  
  Espera entre tentativas

- `--retry-max-time <s>`  
  Tempo total de tentativas

- `-z, --time-cond <data>`  
  Condição de tempo para baixar

- `--speed-limit <velocidade>`, `--speed-time <s>`  
  Aborta transferências lentas

## Protocolos
- `--http0.9`, `--http1.0`, `--http1.1`, `--http2`, `--http3`, `--http3-only`  
  Versões HTTP

- `--proto`, `--proto-redir`, `--proto-default`  
  Controle de protocolos permitidos

- `--ftp-*`  
  Diversas opções FTP

- `--socks*`  
  Várias opções para proxies SOCKS

- `--unix-socket <caminho>`, `--abstract-unix-socket <caminho>`  
  Usar soquetes Unix

## Diversos
- `-#, --progress-bar`  
  Barra de progresso

- `--help`, `--manual`  
  Ajuda e manual completo

- `--version`, `-V`  
  Mostra versão

- `--libcurl <arquivo>`  
  Gera código em C usando libcurl

- `--write-out <formato>`, `-w`  
  Saída customizada

- `--output-dir <diretório>`  
  Diretório para salvar arquivos

- `--remote-header-name`, `-J`  
  Usa nome do cabeçalho `Content-Disposition`

- `--remote-name-all`  
  Aplica `--remote-name` a todas as URLs

- `--remove-on-error`  
  Remove arquivo em caso de erro

- `--resolve <host:porta:endereço>`  
  Força resolução de DNS

- `--next`  
  Reinicia opções para próxima URL

- `--no-alpn`, `--no-npn`  
  Desativa ALPN/NPN

- `--no-buffer`, `-N`  
  Desativa buffer do stdout

- `--no-clobber`  
  Não sobrescreve arquivos existentes

- `--no-progress-meter`  
  Oculta medidor de progresso

- `--no-sessionid`  
  Desativa ID de sessão SSL

- `--path-as-is`  
  Usa caminho literal

- `--pubkey <arquivo>`  
  Chave pública SSH

- `--quote <comando>`, `-Q`  
  Envia comandos antes da transferência

- `--random-file <arquivo>`  
  Fonte de entropia

- `--skip-existing`  
  Ignora download se arquivo já existir

- `--suppress-connect-headers`  
  Suprime cabeçalhos CONNECT

- `--xattr`  
  Usa atributos estendidos

- `--url <url>`  
  Define URL

- `--url-query <dados>`  
  Adiciona parâmetros à query

- `--variável <nome=valor>`  
  Define variáveis para uso com `@arquivo`

- `--etag-compare <arquivo>`  
  Compara ETag

- `--etag-save <arquivo>`  
  Salva ETag

## E-mail (SMTP/IMAP/POP3)
- `--mail-from <endereço>`  
  Remetente

- `--mail-rcpt <endereço>`  
  Destinatário

- `--mail-auth <endereço>`  
  Autenticação SMTP

- `--mail-rcpt-allowfails`  
  Permite falha no RCPT TO

## HTTP Avançado
- `--http2-prior-knowledge`  
  Usa HTTP/2 direto

- `--expect100-timeout <s>`  
  Espera por `100-continue`

- `--ignore-content-length`  
  Ignora `Content-Length`

- `--request-target <caminho>`  
  Alvo alternativo

- `--http0.9`  
  Permite resposta HTTP 0.9

- `--false-start`  
  Ativa False Start TLS

## HSTS, DoH e Segurança
- `--hsts <arquivo>`  
  Ativa HTTP Strict Transport Security

- `--doh-url <URL>`  
  DNS-over-HTTPS

- `--doh-insecure`, `--doh-cert-status`  
  Verificações DoH

- `--dump-ca-embed`  
  Imprime CAs embutidas

- `--hostpubmd5 <md5>`, `--hostpubsha256 <sha256>`  
  Verificação da chave pública do host

## Multiplexação e Paralelismo
- `-Z, --parallel`  
  Transferências paralelas

- `--parallel-max <n>`  
  Máximo de paralelas

- `--parallel-immediate`  
  Inicia sem aguardar

## Configuração e Arquivos
- `-K, --config <arquivo>`  
  Lê opções de arquivo

- `-n, --netrc`, `--netrc-optional`, `--netrc-file <arquivo>`  
  Autenticação via `.netrc`

- `--metalink`  
  Usa arquivo metalink XML

## Telnet e TFTP
- `-t, --telnet-option <opt=val>`  
  Opções Telnet

- `--tftp-blksize <valor>`  
  Tamanho de bloco para TFTP

- `--tftp-no-options`  
  Desativa opções de TFTP
