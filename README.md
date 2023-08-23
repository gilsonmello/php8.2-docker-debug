# Configurando o PHP 8.2 com Linux, Docker, Laravel e Xdebug no VScode

- [ ] Instale a extensão Xdebug(https://marketplace.visualstudio.com/items?itemName=xdebug.php-debug)
- [ ] No menu "Run and Debug", clique em "create a launch.json file" e escolha a opção PHP
![WhatsApp Image 2023-08-11 at 05 05 00](https://github.com/gilsonmello/php56-docker-xdebug/assets/13243336/cd1d57d8-5e06-4e63-923f-00af659f23af)
- [ ] Abra o arquivo launch.json e substitua com a configuração abaixo
```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Listen for Xdebug",
      "type": "php",
      "request": "launch",
      "port": 9000,
      "pathMappings": {
        "/var/www/app": "${workspaceFolder}"
      },
      "ignore": [
        "**/vendor/**/*.php"
      ]
    }
  ]
}
```
- [ ] No menu "Run and Debug", Selecione a opção "Listen for Xdebug" e clique no botão "Play" ou "Start Debugging (F5)"
![WhatsApp Image 2023-08-11 at 05 03 53](https://github.com/gilsonmello/php56-docker-xdebug/assets/13243336/d71ddbd1-bdba-4929-928c-f2e5d5e3f838)
- [ ] Abra o terminal e suba os containers php e nginx com o comando
```bash
docker compose up -d
```
- [ ] Abra o arquivo public/index.php e coloque breakpoint em alguma linha de execução
- [ ] Por último, em um browser, rode o link http://localhost:8080 e o breakpoint deve travar a execução do fluxo
