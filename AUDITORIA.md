# Auditoria pública: CONECT PRO, Dragon Unlocker e KENNCELLSERVER

**Data da coleta:** 2 de novembro de 2026  
**Escopo:** revisão passiva das páginas públicas; sem login, compras, exploração, varredura de portas, submissão de formulários ou teste de APIs privadas.

## Resumo executivo

Foram avaliados os conteúdos públicos de [conectproo.com](https://conectproo.com/) e [kenncellserver.com](https://kenncellserver.com/). A página de [dracounlocker.com](https://dracounlocker.com/) não pôde ser carregada pelo navegador de auditoria nas tentativas HTTPS, HTTP redirecionado e `www`; portanto, não há achados técnicos confiáveis para esse domínio nesta rodada.

Os dois sites acessíveis apresentam vitrines de serviços e licenças para ferramentas de reparo/desbloqueio de dispositivos, com termos de uso, cadastros que coletam dados pessoais e promessas comerciais de segurança/rapidez. A maior prioridade é tornar coerentes as restrições de uso com o catálogo exibido, identificar claramente a empresa operadora e explicar como os dados de cadastro e pagamento são tratados. Esta revisão não conclui que os serviços sejam ilícitos nem confirma vulnerabilidades técnicas.

## Metodologia e limites

- Leitura automatizada das páginas públicas e conteúdo visível indexado.
- Não foram testados TLS/certificados, cabeçalhos HTTP, cookies, CSP, controle de acesso, autenticação, dependências, código-fonte ou segurança do checkout.
- Não foi criado cadastro nem transmitida informação a qualquer site.
- Links de políticas foram identificados, mas seu conteúdo integral e validade jurídica não foram verificados.
- Severidade indica prioridade de revisão com base no impacto potencial e evidência pública, não uma confirmação de exploração.

## Achados

### CP-01 — Restrições de uso não estão refletidas claramente no catálogo

**Severidade: Alta | Tipo: governança, confiança e risco jurídico**

No CONECT PRO, o modal declara que o usuário deve usar os serviços somente em aparelhos próprios ou autorizados e proíbe remoção de bloqueios sem autorização. Ao mesmo tempo, a página anuncia itens descritos como MDM bypass, FRP e passcode/Hello. Essa combinação pode ser interpretada como contraditória pelo cliente e dificulta demonstrar que controles de autorização são aplicados antes da prestação do serviço.

**Recomendação:** exigir prova de titularidade/autorização quando aplicável; esclarecer quais serviços são suportados e as condições de elegibilidade em cada página de produto; registrar a decisão e a evidência mínima necessária; remover anúncios ambíguos que não possam ser oferecidos de modo autorizado.

### CP-02 — Identificação comercial e localização parecem dados genéricos/inconsistentes

**Severidade: Alta | Tipo: transparência e prevenção a fraude**

O rodapé informa telefone brasileiro, horário GMT e o endereço “123 San Francisco, CA 94105, USA”. A combinação de telefone brasileiro com um endereço aparentemente genérico dos EUA reduz a capacidade do usuário de identificar a parte contratada e buscar suporte ou contestação.

**Recomendação:** publicar razão social/nome empresarial, país, endereço real de atendimento, canal de suporte verificável e horários com fuso identificado. Se o endereço não for local de atendimento, explicar sua finalidade.

### CP-03 — Recolha de dados cadastrais sem contexto suficiente na página de entrada

**Severidade: Alta | Tipo: privacidade**

O cadastro visível pede nome, e-mail, celular, moeda, país, cidade, endereço e senha. A página aponta para uma política de privacidade, mas a revisão desta rodada não verificou seu conteúdo, versão, controlador, finalidades, retenção, compartilhamentos e meios de exercício de direitos.

**Recomendação:** antes do cadastro, apresentar aviso curto com operador/controlador, finalidades por campo, retenção, compartilhamentos (inclusive pagamentos e mensageria), canal de privacidade e link para política completa. Rever se endereço e moeda são necessários para todos os usuários.

### CP-04 — Promessas absolutas de segurança e rapidez sem prova apresentada

**Severidade: Média | Tipo: comunicação e confiança**

O site declara “100% Secure”, “SSL encrypted platform” e resultados em minutos. HTTPS/criptografia em trânsito, mesmo que presente, não comprova segurança integral da plataforma, do armazenamento, dos fornecedores ou dos processos.

**Recomendação:** trocar promessas absolutas por afirmações delimitadas e verificáveis; publicar práticas de segurança e canais de reporte; medir prazos e comunicar exceções.

### CP-05 — Idioma, unidades e conteúdo comercial inconsistentes

**Severidade: Média | Tipo: experiência e qualidade**

A interface mistura português e inglês, apresenta valores em USD em páginas voltadas ao Brasil, contém erros textuais como “Miniutes” e discrepâncias de grafia entre listas e produtos. Isso pode confundir preço, moeda, prazo e expectativa de entrega.

**Recomendação:** padronizar idioma, moeda e formatos; mostrar preço final, taxas/câmbio, prazo e condições de reembolso; validar os textos e os mesmos dados em vitrines, produto e checkout.

### KC-01 — Link de contato/imagem aponta para domínio externo diferente

**Severidade: Alta | Tipo: integridade de links e confiança**

Na página do KENNCELLSERVER, a imagem/ação rotulada como WhatsApp aparece associada a `ibypassing-activador.net`, enquanto outro link de contato leva a `api.whatsapp.com`. A relação entre esse domínio externo e a marca não fica explicada na página.

**Recomendação:** substituir por link oficial controlado ou explicar claramente o operador terceiro; validar todos os destinos de contato e afiliados; aplicar `rel="noopener noreferrer"` a links em nova aba onde cabível.

### KC-02 — Dados de contato e endereço também parecem genéricos/inconsistentes

**Severidade: Alta | Tipo: transparência e prevenção a fraude**

O rodapé mistura telefone brasileiro, horário GMT e “123 San Francisco, CA 94105, USA”. O e-mail e telefone estão visíveis, mas a identidade jurídica e a relação com o endereço não ficam claras.

**Recomendação:** publicar dados verificáveis da entidade responsável, suporte e jurisdição; explicar eventual endereço administrativo; manter contatos consistentes entre rodapé, políticas e canais externos.

### KC-03 — Cadastro coleta endereço e telefone; política precisa ser validada

**Severidade: Alta | Tipo: privacidade**

O fluxo público de criação de conta solicita nome, e-mail, número móvel, moeda, país, cidade, endereço e senha. A página lista uma política de privacidade, mas seu conteúdo não foi avaliado nesta coleta.

**Recomendação:** apresentar aviso de privacidade antes da coleta, validar necessidade de cada campo e documentar retenção, acesso, compartilhamento, segurança e exclusão.

### KC-04 — Catálogo de bypass e aluguel de ferramentas exige controle de autorização

**Severidade: Alta | Tipo: governança e risco jurídico**

A página anuncia serviços descritos como bypass de iCloud/FRP, passcode/Hello e aluguel de ferramentas. A página inicial consultada não evidencia no conteúdo extraído um fluxo de validação de titularidade para cada pedido. Isso é uma lacuna de evidência pública, não prova de ausência de controle no checkout ou no back-end.

**Recomendação:** documentar critérios de elegibilidade, obter autorização verificável quando necessária e informar o processo antes da compra; auditar os controles internos e os registros de decisão.

### KC-05 — Declarações “100% Secure” e “Instant” devem ser delimitadas

**Severidade: Média | Tipo: comunicação e confiança**

As promessas de segurança total e entrega instantânea não indicam escopo, exceções, métricas ou dependências de terceiros.

**Recomendação:** usar afirmações mensuráveis e explicitar condições, prazos típicos, falhas de fornecedores e processo de reembolso.

### DR-01 — Domínio não acessível na coleta

**Severidade: Não classificada | Tipo: disponibilidade/limite da auditoria**

O navegador de auditoria não conseguiu carregar `dracounlocker.com` com HTTPS, nem as tentativas HTTP e `www` (que foram redirecionadas/normalizadas para o mesmo destino não acessível). Isso pode decorrer de indisponibilidade, bloqueio automatizado, DNS/TLS ou limitação da ferramenta; não é possível determinar a causa a partir desta evidência.

**Recomendação:** repetir a coleta de uma rede/navegador autorizado e confirmar DNS, redirecionamentos, certificado e resposta HTTP antes de atribuir um problema ao site.

## Plano de ação sugerido

1. **Imediato:** esclarecer titularidade/autorização e elegibilidade nos produtos de maior risco; revisar os links de contato do KENNCELLSERVER.
2. **Curto prazo:** corrigir a identificação comercial e alinhar telefone, endereço, país, horários e canais oficiais.
3. **Curto prazo:** revisar os formulários e avisos de privacidade, minimizando dados obrigatórios.
4. **Próxima rodada técnica:** com autorização expressa do operador, coletar cabeçalhos/TLS/cookies, revisar páginas de políticas, testar acessibilidade e validar fluxos de autenticação/checkout sem concluir compras.
5. **Próxima rodada Dragon Unlocker:** repetir a coleta pública quando o domínio estiver acessível e registrar timestamp, DNS, redirecionamentos e resposta HTTP.

## Fontes públicas consultadas

- CONECT PRO: https://conectproo.com/
- KENNCELLSERVER: https://kenncellserver.com/
- Dragon Unlocker (não acessível nesta coleta): https://dracounlocker.com/
