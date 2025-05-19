# Opções de Linha de Comando `curl` Formatadas

## Autenticação
- `--anyauth`  
  Tenta automaticamente selecionar o método de autenticação mais apropriado suportado pelo servidor (como Basic, Digest, NTLM, Negotiate, etc.).

- `--aws-sigv4 <provider>`  
  Utiliza o esquema de autenticação AWS Signature Version 4 com o provedor especificado, geralmente para acessar APIs da AWS de forma segura.

- `--basic`  
  Força o uso de autenticação HTTP Basic, enviando nome de usuário e senha codificados em Base64 (não é seguro sem HTTPS).

- `--digest`  
  Utiliza autenticação HTTP Digest, que é mais segura que a Basic por usar hashing.

- `--negotiate`  
  Usa autenticação baseada em Negotiate (SPNEGO), com suporte a Kerberos, frequentemente usada em ambientes corporativos.

- `--proxy-anyauth`  
  Tenta automaticamente selecionar o melhor método de autenticação suportado pelo servidor proxy.

- `--proxy-basic`  
  Força o uso de autenticação Basic com o servidor proxy.

- `--proxy-digest`  
  Usa autenticação Digest com o proxy, para maior segurança que a Basic.

- `--proxy-negotiate`  
  Utiliza autenticação Negotiate com o proxy, com suporte a mecanismos como Kerberos.

- `--proxy-ntlm`  
  Usa o protocolo NTLM (da Microsoft) para autenticação com o proxy.

- `--sasl-authzid <identidade>`  
  Define a identidade de autorização SASL a ser usada durante a autenticação (diferente do login).

- `--sasl-ir`  
  Envia a resposta inicial SASL automaticamente, útil para conexões mais rápidas em alguns servidores.

- `--krb <nível>`  
  Ativa autenticação Kerberos. O `<nível>` pode controlar como a segurança da conexão é tratada (ex: `clear`, `safe`, `confidential`,` private`).

- `-u, --user <usuário:senha>`  
  Define o nome de usuário e a senha a serem usados para autenticação no servidor, separados por dois-pontos.

- `-U, --proxy-user <usuário:senha>`  
  Fornece credenciais para autenticação no servidor proxy.

## Certificados e TLS
- `--ca-native`  
  Usa os certificados de autoridades certificadoras (CAs) instalados no sistema operacional para validar conexões TLS/SSL.
  
- `--cacert <arquivo>`  
  Especifica um arquivo contendo certificados CA em formato PEM para validar o certificado do servidor (substitui o padrão do sistema).

- `--capath <dir>`  
  Fornece um diretório contendo múltiplos arquivos de certificados CA, um por arquivo, para validar o peer.

- `-E, --cert <arquivo[:senha]>`  
  Usa um certificado de cliente para autenticação mútua. Pode incluir uma senha se o certificado estiver criptografado.

- `--cert-type <tipo>`  
  Especifica o formato do certificado fornecido com `--cert` (ex: PEM, DER, ENG, P12).

- `--cert-status`  
  Solicita ao servidor um verificador OCSP para confirmar que o certificado não foi revogado.

- `--ciphers <lista>`  
  Define quais algoritmos de criptografia TLS devem ser utilizados, conforme suportado pela biblioteca TLS usada.

- `--curves <lista>`  
  Lista as curvas elípticas preferidas (ECC) para negociação de TLS, como `prime256v1`, `secp521r1`, etc.

- `--crlfile <arquivo>`  
  Especifica um arquivo contendo uma lista de revogação de certificados (CRL) para checar se um certificado foi revogado.

- `--key <arquivo>`  
  Caminho para a chave privada correspondente ao certificado de cliente especificado com `--cert`.

- `--key-type <tipo>`  
  Define o tipo da chave privada (PEM, DER ou ENG).

- `--pinnedpubkey <hashes>`  
  Valida a chave pública do servidor contra um hash pré-definido, protegendo contra ataques de interceptação (MITM).

- `--ssl`, `--ssl-reqd`  
  Força o uso de SSL/TLS na conexão. _`--ssl-reqd` aborta a conexão se não for possível negociar segurança.

- `--ssl-allow-beast` 
  Permite o uso de cifras vulneráveis ao ataque BEAST, útil para compatibilidade com servidores antigos.

- `--ssl-no-revoke`
  Desativa a verificação de revogação de certificados, mesmo que disponível.

- `--ssl-revoke-best-effort`
  Tenta verificar a revogação, mas não falha caso não seja possível.

- `--ssl-auto-client-cert`
  Permite que `curl` use automaticamente um certificado de cliente gerenciado pelo sistema.

- `--tls-max <VERSÃO>`  
  Define a versão máxima do protocolo TLS permitida (ex: `1.2`, `1.3`).

- `--tls13-ciphers <lista>`  
  Lista os conjuntos de cifras preferidas especificamente para conexões TLS 1.3.

- `--tlsauthtype <tipo>`  
  Especifica o tipo de autenticação TLS a ser usada (por exemplo, `SRP`).

- `--tlspassword <senha>`
  Senha usada com `--tlsuser` para autenticação baseada em TLS.

- `--tlsuser <usuário>`
  Nome de usuário para autenticação TLS (como TLS-SRP).

- `-2`, `--sslv2`  
  Força o uso do protocolo SSL versão 2 (obsoleto e inseguro).

- `-3`, `--sslv3`
  Força o uso do protocolo SSL versão 3 (também considerado inseguro).

- `--tlsv1.x`
  Força o uso de uma versão específica do protocolo TLS (ex: --tlsv1.2).

## Conexão e Rede
- `--connect-timeout <segundos>`  
  Define o tempo máximo (em segundos) para o curl estabelecer uma conexão com o servidor antes de desistir.

- `--connect-to <HOST1:PORT1:HOST2:PORT2>`  
  Redireciona internamente a conexão da origem (HOST1:PORT1) para um destino alternativo (HOST2:PORT2), útil para testes ou substituição de hosts.

- `--interface <nome>`  
  Especifica a interface de rede a ser usada para a conexão (ex: `eth0`, `wlan0`, ou endereço IP local).

- `--dns-interface`  
  Define a interface de rede que deve ser usada especificamente para consultas DNS.

- `--dns-ipv4-addr`
  Usa um endereço IPv4 específico como origem ao fazer requisições DNS.

- `--dns-ipv6-addr`
  Usa um endereço IPv6 específico como origem ao fazer requisições DNS.

- `--dns-servers`
  Especifica servidores DNS personalizados a serem usados nas consultas, separados por vírgula (ex: `8.8.8.8`, `1.1.1.1`).

- `--happy-eyeballs-timeout-ms <milissegundos>`  
  Tempo de espera antes de tentar uma conexão IPv4 quando uma conexão IPv6 está em andamento. Ajuda a acelerar conexões em redes com suporte instável a IPv6.

- `-4`, `--ipv4` / `-6`, `--ipv6`  
  Forçar IPv4 ou IPv6

- `--local-port <intervalo>`  
  Especifica a(s) porta(s) locais que o `curl` deve tentar usar para a origem da conexão (ex: `3000-3010`).

- `--rate <velocidade>`  
  Limita a taxa de transferência total (upload/download) da requisição, aceitando formatos como `500K`, `10M`, etc.

- `--tcp-fastope`  
  Habilita o recurso TCP Fast Open, que reduz o tempo de estabelecimento da conexão em sistemas que o suportam.

- `--tcp-nodelay`
  Desativa o algoritmo de Nagle, fazendo com que os dados sejam enviados imediatamente, útil para conexões com baixa latência.

## Cookies
- `-b, --cookie <dados|arquivo>`  
  Envia cookies personalizados com a requisição. Pode ser um valor direto (`chave=valor`) ou um caminho para um arquivo com cookies.

- `-c, --cookie-jar <arquivo>`  
  Salva todos os cookies recebidos durante a sessão em um arquivo especificado para uso futuro.

- `-j, --junk-session-cookies`  
  Ignora cookies temporários de sessão e só armazena cookies persistentes.

## Redirecionamento
- `-L, --location`  
  Segue automaticamente redirecionamentos HTTP 3xx (ex: 301, 302).

- `--location-trusted`  
  Segue redirecionamentos e inclui credenciais de autenticação automaticamente nos novos destinos.

- `--max-redirs <num>`  
  Limita a quantidade de redirecionamentos que podem ser seguidos.

- `--post301`, `--post302`, `--post303`  
  Mantém o método `POST` ao seguir redirecionamentos 301, 302 ou 303 (por padrão, `curl` muda para `GET`).

## Proxy
- `-x, --proxy [proto://]host[:port]`  
  Especifica um servidor proxy a ser usado (ex: `http://proxy.local:8080`).

- `--proxy-cert <cert[:senha]>`  
  Certificados e segurança do proxy

- `--proxy-key <arquivo>`
  Chave privada correspondente ao certificado do proxy.

- `--proxy-cacert <arquivo>`
  Certificado da autoridade certificadora para validação do proxy.

- `--proxy-crlfile <arquivo>`
  Lista de revogação de certificados (CRL) usada ao se conectar via proxy.

- `--proxy-insecure`  
  Ignora erros de verificação de certificado SSL do proxy.

- `--proxytunnel`  
  Cria um túnel HTTP por meio do método CONNECT, útil para HTTPS através de proxy.

- `--proxy1.0 <host[:port]>`  
  Força o uso de proxy HTTP 1.0.

## Download/Upload
- `-o, --output <arquivo>`  
  Salva a resposta da requisição em um arquivo com nome definido.

- `-O, --remote-name`  
  Salva o conteúdo com o mesmo nome do arquivo remoto (baseado no caminho da URL).

- `-T, --upload-file <arquivo>`  
  Envia o conteúdo de um arquivo como corpo da requisição PUT.

- `-C, --continue-at <offset>`  
  Retoma um download interrompido a partir de um ponto específico.

- `--create-dirs`  
  Cria automaticamente diretórios locais necessários para salvar arquivos.

- `--create-file-mode <modo>`  
  Define as permissões (modo) para arquivos criados durante o download.

- `--limit-rate <velocidade>`  
  Limita a taxa de transferência (ex: `100K`, `1M`), útil para não saturar a conexão.

## Método de Requisição
- `-d, --data <dados>`  
  Envia dados via método `POST`. O conteúdo é incluído no corpo da requisição.

- `--data-ascii`, `--data-binary`, `--data-urlencode`, `--data-raw`  
  Variações para o envio de dados com controle de codificação e interpretação.

- `-F, --form <campo=conteúdo>`  
  Envia dados via `multipart/form-data`, ideal para formulários com arquivos.

- `--form-string` 
  Como `--form`, mas trata o conteúdo literalmente (sem interpretação de `@` ou arquivos).

- `--form-escape` 
  Escapa automaticamente caracteres especiais nos dados de formulário.

- `-G, --get`  
  Converte a requisição para `GET` e adiciona os dados como parâmetros de URL.

- `-X, --request <método>`  
  Define manualmente o método HTTP a ser usado (ex: `PUT`, `DELETE`, `PATCH`).

## Cabeçalhos
- `-H, --header <cabeçalho>`  
  Adiciona cabeçalhos HTTP personalizados à requisição.

- `--proxy-header <cabeçalho>`  
  Envia cabeçalhos HTTP específicos apenas para o proxy.

- `-e, --referer <URL>`  
  Define o valor do cabeçalho `Referer`, informando a origem da requisição.

- `-A, --user-agent <nome>`  
  Define o cabeçalho `User-Agent` enviado com a requisição.

## Logs e Debug
- `-v, --verbose`  
  Exibe detalhes completos de toda a transação HTTP.

- `-s, --silent`  
  Executa silenciosamente, sem mostrar barra de progresso ou mensagens.

- `-S, --show-error`  
  Mostra mensagens de erro mesmo quando em modo silencioso - `-s`.

- `--trace <arquivo>`
  Grava todas as atividades em um arquivo de rastreamento detalhado.
  
- `--trace-ascii`
  Grava rastreamento apenas com caracteres imprimíveis (ASCII).
  
- `--trace-time`
  Inclui timestamp em cada linha do rastreamento.
  
- `--trace-ids`
  Exibe IDs de rastreamento de conexões paralelas.
  
- `--trace-config`
  Mostra configuração de rastreio aplicada.  

- `--styled-output`  
  Exibe saída com cores e formatação, quando disponível.

- `--stderr <arquivo>`  
  Redireciona a saída de erro - `stderr` - para um arquivo específico.

## Tempo e Condições
- `-m, --max-time <segundos>`  
  Define o tempo máximo total permitido para a requisição (incluindo conexão e transferência).

- `--retry <número>`  
  Tenta novamente em caso de falha na conexão ou requisição, até o número especificado.

- `--retry-delay <segundos>`  
  Aguarda um tempo entre cada tentativa de nova conexão.

- `--retry-max-time <segundos>`  
  Tempo total máximo (incluindo tentativas) para concluir a operação.

- `-z, --time-cond <data>`  
  Executa o download apenas se o conteúdo foi modificado após a data ou timestamp do arquivo.

- `--speed-limit <velocidade>` 
  Considera a conexão lenta se a velocidade cair abaixo desse valor.

- `--speed-time <segundos>` 
  Tempo que a velocidade deve estar abaixo do limite para abortar a transferência.

## Protocolos
- `--http0.9`, `--http1.0`, `--http1.1`, `--http2`, `--http3`, `--http3-only`  
  Força o uso de uma versão específica do protocolo HTTP.

- `--proto <protocolo>`  
  Define quais protocolos são permitidos na conexão (ex: http,https,ftp).

- `--proto-redir <protocolo>`
  Define protocolos permitidos para redirecionamentos.
  
- `--proto-default <protocolo>`
  Define o protocolo padrão a ser usado se a URL não o especificar.

- `--ftp-*`  
  Várias opções para FTP, como modo ativo, passivo, SSL, etc.

- `--socks*`  
  Define proxy do tipo SOCKS4, SOCKS5 e variações com autenticação.

- `--unix-socket <caminho>`
  Usa um socket Unix local para comunicação ao invés de TCP/IP.

- `--abstract-unix-socket <caminho>`
  Usa socket Unix abstrato (Linux).

## Diversos
- `-#, --progress-bar`  
  Exibe uma barra de progresso no estilo visual.

- `--help`, `--manual`  
  Exibe ajuda breve ou o manual completo.
  
- `--version`, `-V`  
  Mostra a versão do `curl` instalada.

- `--libcurl <arquivo>`  
  Gera um código em C usando a libcurl com base nos parâmetros usados.

- `--write-out <formato>`, `-w`  
  Exibe estatísticas ou informações específicas após a operação.

- `--output-dir <diretório>`  
  Define o diretório onde os arquivos baixados serão salvos.

- `--remote-header-name`, `-J`  
  Usa o nome do arquivo definido pelo servidor no cabeçalho `Content-Disposition`.

- `--remote-name-all`  
  Aplica `--remote-name` a todas as URLs especificadas.

- `--remove-on-error`  
  Apaga arquivos parcialmente baixados se ocorrer erro durante o processo.
  
- `--resolve <host:porta:endereço>`  
  Substitui a resolução de DNS para um host específico, útil para testes.

- `--next`  
  Recomeça o processamento de opções para a próxima URL na linha de comando.

- `--no-alpn`, `--no-npn`  
  Desativa suporte a negociações de protocolos ALPN ou NPN (TLS).

- `--no-buffer`, `-N`  
  Desativa suporte a negociações de protocolos ALPN ou NPN (TLS).

- `--no-clobber`  
  Evita sobrescrever arquivos existentes durante o download.

- `--no-progress-meter`  
  Oculta a exibição do medidor de progresso.

- `--no-sessionid`  
  Desativa o reuso de identificadores de sessão SSL.

- `--path-as-is`  
  Usa o caminho da URL exatamente como fornecido, sem modificações.

- `--pubkey <arquivo>`  
  Fornece chave pública para autenticação SSH.
  
- `--quote <comando>`, `-Q`  
  Envia comandos personalizados para o servidor antes da transferência (ex: comandos FTP).

- `--random-file <arquivo>`  
  Usa um arquivo como fonte de entropia para operações criptográficas.

- `--skip-existing`  
  Pula o download de arquivos que já existem localmente.

- `--suppress-connect-headers`  
  Remove cabeçalhos extras da resposta CONNECT (em proxies).

- `--xattr`  
  Armazena metadados da transferência como atributos estendidos de arquivo (no Linux/macOS).

- `--url <url>`  
  Define explicitamente a URL a ser usada.

- `--url-query <dados>`  
  Adiciona parâmetros à query da URL (mesmo se já existir uma).

- `--variável <nome=valor>`  
  Define variáveis que podem ser referenciadas em arquivos `@config`.

- `--etag-compare <arquivo>`  
  Faz download apenas se a ETag for diferente da armazenada no arquivo.

- `--etag-save <arquivo>`  
  Salva a ETag recebida para uso posterior.

## E-mail (SMTP/IMAP/POP3)
- `--mail-from <endereço>`  
  Define o remetente da mensagem ao enviar e-mails via SMTP.

- `--mail-rcpt <endereço>`  
  Define os destinatários do e-mail.

- `--mail-auth <endereço>`
  Define o endereço para autenticação SMTP (caso seja diferente do remetente).
  
- `--mail-rcpt-allowfails`  
  Permite que falhas em alguns destinatários não cancelem a operação.

## HTTP Avançado
- `--http2-prior-knowledge`  
  Usa HTTP/2 diretamente sem negociação via ALPN/NPN.

- `--expect100-timeout <segundos>`  
  Tempo de espera por uma resposta `100-continue` do servidor antes de enviar o corpo da requisição.

- `--ignore-content-length`  
  Ignora o cabeçalho `Content-Length` do servidor e continua lendo até o fim da conexão.

- `--request-target <caminho>`  
  Alvo alternativo para a linha de requisição HTTP (útil para proxies).

- `--http0.9`  
  Permite respostas no formato HTTP 0.9, usadas em servidores antigos.

- `--false-start`  
  Permite iniciar a comunicação antes de finalizar o handshake TLS (em sistemas que suportam).

## HSTS, DoH e Segurança
- `--hsts <arquivo>`  
  Armazena e aplica políticas de HTTP Strict Transport Security (HSTS).

- `--doh-url <URL>`  
  Usa um servidor DNS-over-HTTPS específico para resolver nomes.

- `--doh-insecure`  
  Ignora problemas de certificado ao usar DoH.

- `--doh-cert-status`
  Ativa verificação de status de certificado no DoH.

- `--dump-ca-embed`  
  Exibe certificados CA embutidos no `curl`.

- `--hostpubmd5 <md5>`, `--hostpubsha256 <sha256>`  
  Verifica se a chave pública do host corresponde ao hash fornecido.

## Multiplexação e Paralelismo
- `-Z, --parallel`  
  Habilita transferências simultâneas (paralelas) de múltiplas URLs.

- `--parallel-max <n>`  
  Limita o número máximo de transferências paralelas.

- `--parallel-immediate`  
  Inicia as transferências em paralelo sem esperar por configurações adicionais.

## Configuração e Arquivos
- `-K, --config <arquivo>`  
  Lê opções de linha de comando a partir de um arquivo de configuração.

- `-n, --netrc`, `--netrc-optional`, `--netrc-file <arquivo>`  
  Usa o arquivo `.netrc` para autenticação automática com servidores.

- `--metalink`  
  Usa um arquivo metalink (XML) como fonte de URLs alternativas para download.

## Telnet e TFTP
- `-t, --telnet-option <opt=val>`  
  Define opções específicas para conexões Telnet.

- `--tftp-blksize <valor>`  
  Define o tamanho de bloco a ser usado em transferências TFTP.

- `--tftp-no-options`  
  Desativa opções extras ao usar o protocolo TFTP.
