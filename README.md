# Miniguia de Segurança para Desenvolvedores (DevSecOps & Mobile)

Este guia consolida práticas essenciais para a implementação de segurança em aplicações desde o início do ciclo de desenvolvimento (**Shift-Left**), focando em metodologias DevSecOps e segurança em dispositivos móveis.

## 1. Fundamentos de DevSecOps
O **DevSecOps** é a integração da segurança em todos os níveis do ciclo de vida de desenvolvimento de software (SDLC). O objetivo principal é tornar todos os envolvidos responsáveis pela segurança, permitindo decisões rápidas e seguras na mesma escala do desenvolvimento e operações.

### O Ciclo de Vida Seguro (SDLC)
*   **Planejamento:** Definir metas, requisitos e estratégias de segurança, avaliando ameaças precocemente.
*   **Desenvolvimento:** Identificar e corrigir vulnerabilidades enquanto o código é escrito.
*   **Testes:** Executar análise de código, testes de vulnerabilidade e penetração.
*   **Implantação:** Garantir configurações corretas no ambiente de produção.
*   **Monitoramento:** Detectar continuamente ameaças e agir rapidamente para mitigá-las.

## 2. Automação e Ferramentas (SAST e DAST)
A automação é um pilar do DevSecOps, integrando segurança em esteiras de **CI/CD** (Integração e Entrega Contínua).

*   **SAST (Static Application Security Testing):** Analisa o código-fonte em busca de falhas (como erros de programação e segredos expostos) durante o desenvolvimento.
    *   *Ferramentas sugeridas:* **SonarQube**, **Checkmarx**, Fortify e Veracode.
*   **DAST (Dynamic Application Security Testing):** Testa a aplicação em tempo de execução para identificar falhas de autenticação, injeção de SQL e outras ameaças reais.
    *   *Ferramentas sugeridas:* **OWASP ZAP**, Burp Suite e Invicti (antigo Netsparker).

## 3. Melhores Práticas de Segurança em Aplicações
### Arquitetura e Design
*   **Secure by Design:** A segurança deve ser um requisito inicial, não uma reflexão tardia.
*   **Princípio do Menor Privilégio:** Solicite apenas as permissões estritamente necessárias para o funcionamento do app.
*   **Não Confie no Cliente:** Realize autenticação e autorização sempre no lado do servidor.

### Proteção de Dados e Comunicação
*   **Criptografia:** Use APIs de plataforma para criptografar dados sensíveis em repouso e em trânsito.
*   **HTTPS:** Utilize obrigatoriamente protocolos seguros para toda comunicação de rede.
*   **Gestão de Segredos:** Nunca utilize credenciais *hardcoded* (fixas no código); prefira tokens de acesso seguros e revogáveis.

## 4. Guia Específico por Plataforma (Mobile)
### Android
*   Use o **Android Keystore** com suporte de hardware (**TEE ou StrongBox**) para armazenar chaves criptográficas.
*   Implemente a **Play Integrity API** para verificar a integridade do dispositivo e do aplicativo.
*   Utilize o **ProGuard** para ofuscação de código e desative o modo de backup para dados sensíveis.

### iOS e iPadOS
*   Utilize o **Secure Enclave** para operações criptográficas sensíveis, garantindo que as chaves nunca saiam do hardware seguro.
*   Implemente a **App Attest API** para validar a integridade da aplicação.
*   Configure permissões rigorosas para **Siri e Atalhos (Shortcuts)**, exigindo desbloqueio do dispositivo para ações sensíveis.

## 5. Curadoria de Fontes e Referências
Este guia foi compilado com base em referências líderes da indústria:

1.  **DevSecOps: Metodologias, ferramentas, certificações e mercado:** Artigo técnico sobre a cultura de integração entre Dev, Sec e Ops.
2.  **OWASP Mobile Application Security (MAS):** *Cheat sheet* e guias de referência para segurança em apps móveis.
3.  **OWASP Top 10 Web Application Security Risks:** Documento padrão de conscientização sobre os riscos mais críticos em aplicações web.

---
*Este documento é um ponto de partida. Recomenda-se a consulta contínua aos projetos da **OWASP Foundation** para atualizações sobre novas vulnerabilidades e técnicas de mitigação.*
