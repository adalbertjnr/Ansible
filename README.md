# Ansible

# Instalação utilizando roles para mysql e dependencias, criação do usuário root para o banco de dados e também criado usuário para o wordpress acessar a base dados.
- mysql/defaults
`Valores que sempre serão alocados na variável, nesse caso 2 hosts`
- mysql/files
`Arquivo de configuração do banco de dados para aceitar conexões remotas`
- mysql/handlers
`Utilizado para recarregar o serviço do mysql após os ajustes feitos acima`
- mysql/tasks
`Arquivo onde todo o processo de instalação é feito`
# Role do webserver responsável por instalação do apache e php com as respectivas dependências
- webserver/tasks
`Arquivo de instalação do apache e php`
# Role do wordpress para instalação do wordpress
- wordpress/meta
`O arquivo meta especifíca todas as dependências, nesse ponto depende da role do webserver`
- worldpress/templates
`O template em .j2 necessário para configuração do apache apontando o arquivo do wordpress -- var/www/wordpress`
# Hosts
`Inventário chamado "hosts" com variáveis para conexão ssh com os hosts para serem configurados`
# playbook
`Onde todas as roles são chamadas para configurar o inventário de hosts`