# 🌐 DNS Overview

## 🇬🇧 English

### 🌍 DNS (Domain Name System)
DNS (Domain Name System) provides a simple way for us to communicate with devices on the internet without remembering complex numbers. 🚀

#### 🏰 Domain Hierarchy
![Domain Hierarchy](/TryHackMe/images/image.png)

#### 📋 Types of DNS
- **A record** 📍: Resolves IPv4 addresses, for example, 104.26.10.229.
- **AAAA record** 🌐: Resolves IPv6 addresses, for example, 2606:4700:20::681a:be5.
- **CNAME records** 🔗: These records resolve to another domain name. For example, TryHackMe's online shop has the subdomain name store.tryhackme.com, which returns a CNAME record shops.shopify.com. Another DNS request would then be made to shops.shopify.com to work out the IP address.
- **MX record** ✉️: These records resolve to the address of the servers that handle email for the domain you are querying. For example, an MX record response for tryhackme.com would look something like alt1.aspmx.l.google.com. These records also come with a priority flag, which tells the client in which order to try the servers, ideal for scenarios where the main server goes down and email needs to be sent to a backup server. 🔄

#### 🔍 What happens when you make a DNS request
1. When you request a domain name, your computer first checks its local cache 🗃️ to see if you've previously looked up the address recently; if not, a request to your Recursive DNS Server is made.
2. A Recursive DNS Server is usually provided by your ISP, but you can also choose your own. This server also has a local cache of recently looked up domain names. If a result is found locally, it is sent back to your computer, and your request ends here (common for popular services like Google, Facebook, Twitter). If the request cannot be found locally, a journey begins to find the correct answer, starting with the internet's root DNS servers. 🌱
3. The root servers act as the DNS backbone of the internet 🌐; their job is to redirect you to the correct Top Level Domain (TLD) Server, depending on your request. For example, if you request www.tryhackme.com, the root server recognizes the Top Level Domain of .com and refers you to the correct TLD server that handles .com addresses.
4. The TLD server holds records for where to find the authoritative server to answer the DNS request. The authoritative server, often called the nameserver for the domain, for tryhackme.com, for example, is kip.ns.cloudflare.com and uma.ns.cloudflare.com. Multiple nameservers are often used as backups in case one goes down. 🛡️
5. An authoritative DNS server is responsible for storing the DNS records for a particular domain name and where updates to DNS records are made. Depending on the record type, the DNS record is sent back to the Recursive DNS Server, where a local copy is cached for future requests and relayed back to the original client. DNS records come with a TTL (Time To Live) value, a number in seconds indicating how long the response should be cached locally before needing to be looked up again. Caching reduces the need for repeated DNS requests. ⏳

![DNS Request Process](/TryHackMe/images/image2.png)

## 🇧🇷 Português

### 🌍 DNS (Sistema de Nomes de Domínio)
O DNS (Sistema de Nomes de Domínio) oferece uma maneira simples de nos comunicarmos com dispositivos na internet sem a necessidade de memorizar números complexos. 🚀

#### 🏰 Hierarquia de Domínios
![Hierarquia de Domínios](/TryHackMe/images/image.png)

#### 📋 Tipos de DNS
- **Registro A** 📍: Resolve endereços IPv4, por exemplo, 104.26.10.229.
- **Registro AAAA** 🌐: Resolve endereços IPv6, por exemplo, 2606:4700:20::681a:be5.
- **Registros CNAME** 🔗: Esses registros resolvem para outro nome de domínio. Por exemplo, a loja online do TryHackMe tem o subdomínio store.tryhackme.com, que retorna um registro CNAME shops.shopify.com. Uma nova solicitação DNS seria feita para shops.shopify.com para descobrir o endereço IP.
- **Registro MX** ✉️: Esses registros resolvem para o endereço dos servidores que gerenciam os e-mails do domínio consultado. Por exemplo, uma resposta de registro MX para tryhackme.com seria algo como alt1.aspmx.l.google.com. Esses registros também incluem uma bandeira de prioridade, que indica ao cliente a ordem para tentar os servidores, ideal para casos em que o servidor principal falha e o e-mail precisa ser enviado para um servidor reserva. 🔄

#### 🔍 O que acontece quando você faz uma solicitação DNS
1. Quando você solicita um nome de domínio, seu computador verifica primeiro seu cache local 🗃️ para ver se o endereço foi consultado recentemente; caso contrário, uma solicitação é feita ao seu Servidor DNS Recursivo.
2. Um Servidor DNS Recursivo é geralmente fornecido pelo seu provedor de internet, mas você também pode escolher o seu próprio. Este servidor também possui um cache local de nomes de domínio consultados recentemente. Se um resultado for encontrado localmente, ele é enviado de volta ao seu computador, e a solicitação termina aqui (comum para serviços populares como Google, Facebook, Twitter). Se a solicitação não for encontrada localmente, começa uma jornada para encontrar a resposta correta, iniciando com os servidores DNS raiz da internet. 🌱
3. Os servidores raiz funcionam como a espinha dorsal do DNS na internet 🌐; seu trabalho é redirecioná-lo ao Servidor de Domínio de Nível Superior (TLD) correto, dependendo da sua solicitação. Por exemplo, se você solicitar www.tryhackme.com, o servidor raiz reconhecerá o Domínio de Nível Superior .com e o encaminhará ao servidor TLD correto que lida com endereços .com.
4. O servidor TLD mantém registros de onde encontrar o servidor autoritativo para responder à solicitação DNS. O servidor autoritativo, muitas vezes chamado de nameserver do domínio, para tryhackme.com, por exemplo, é kip.ns.cloudflare.com e uma.ns.cloudflare.com. Geralmente, há vários nameservers para um domínio como reserva caso um deles falhe. 🛡️
5. Um servidor DNS autoritativo é responsável por armazenar os registros DNS de um determinado nome de domínio e onde as atualizações dos registros DNS são feitas. Dependendo do tipo de registro, o registro DNS é enviado de volta ao Servidor DNS Recursivo, onde uma cópia local é armazenada em cache para solicitações futuras e, em seguida, retransmitida ao cliente original que fez a solicitação. Os registros DNS vêm com um valor TTL (Time To Live), um número em segundos que indica por quanto tempo a resposta deve ser armazenada localmente antes de precisar ser consultada novamente. O armazenamento em cache reduz a necessidade de solicitações DNS repetidas. ⏳

![Processo de Solicitação DNS](/TryHackMe/images/image2.png)