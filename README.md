
1. Título e Objetivo

Projeto: Auditoria de Segurança com Medusa e Kali Linux

    "Este projeto demonstra a simulação de um ataque de força bruta em um ambiente controlado, utilizando o Kali Linux para comprometer o serviço FTP do Metasploitable 2, visando identificar vulnerabilidades e propor medidas de mitigação."

2. Metodologia de Execução

    Ambiente: VirtualBox com rede Host-Only.

    Varredura: Uso do nmap -sV -Pn para identificar a porta 21 (FTP) aberta.

    Resolução de Problemas (Troubleshooting): Documente como você identificou o conflito de IPs e corrigiu a rota configurando manualmente o IP 192.168.56.102.

3. Evidências do Ataque

    Criação da Wordlist: Comandos echo para gerar o arquivo senhas.txt.

    Exploração com Medusa:
    medusa -h 192.168.56.102 -u msfadmin -P senhas.txt -M ftp

    Confirmação de Acesso: O comando ls -l dentro do FTP mostrando a pasta vulnerable.

4. Conclusão e Medidas Preventivas

Como Desenvolvedor Full Stack e futuro especialista em Cybersecurity, finalize com o olhar de prevenção:

    Substituição de Protocolos: Trocar FTP por SFTP (SSH File Transfer Protocol).

    Fortalecimento de Credenciais: Proibir o uso de senhas padrão (default) como msfadmin.

    Implementação de Fail2Ban: Para bloquear IPs que realizam múltiplas tentativas falhas.
