# ESP32-MicroPython
Passo a passo de como configurar e programar seu ESP32 em MicroPython

<p align="center">
    <img src=./img/LogoMicroPython.jpg height="100">
</p>
O MicroPython é uma implementação mínima da linguagem de programação Python, otimizada para sistemas embarcados e microcontroladores. Ele permite que os desenvolvedores programem microcontroladores de forma simples e eficiente, usando a sintaxe familiar da liguagem Python...
<br></br>

# Instação
Como pré requisito para a utilização de MicroPython usando o PyMakr você deve ter instalado em seu computador os seguintes softwares:

-[Visual Studio Code](https://code.visualstudio.com/)

-[NodeJS](https://nodejs.org/en)

-[Python](https://www.python.org/)

Em seu terminal execute o comando a seguir ou baixe o repositorio do [esptool](https://github.com/espressif/esptool)

```shell
git clone https://github.com/espressif/esptool.git
 ```
Abra o diretório que foi baixado
 ```shell
 cd esptool
 ```
 Após ter realizado a instalação dos pré requisitos e o esptool, você deverá baixar a última versão de Firmaware para o ESP32, diretamente no site oficial do [Micro Python](https://micropython.org/), e colocar o arquivo baixado .bin dentro da pasta esptool...

 ⚠️No Windows abra o seu Gerenciador de Dispositivos e verifique em qual porta "COM" o seu ESP32 está conectado

Dentro do terminal execute o seguinte comando para limpar o flash do seu ESP32, lembre-se de substituir a "porta" pela porta do seu ESP32, exemplo: COM3
 ```shell
 python esptool.py --port "porta" erase_flash
 ```
 Após a limpeza do flash do seu ESP32, execute o proximo comando substituindo novamente a "porta" e o "firmaware.bin" pelo nome do firmaware que foi baixado anteriormente...
```shell
python esptool.py --chip esp32 --port "porta" --baud 460800 write_flash --flash_size=detect -z 0x1000 "firmaware.bin"
```
Agora o seu ESP32 já está configurado para receber códigos em MicroPython, mas você deve configurar um ambiente de desenvolvimento para ele...

Dentro do Visual Studio Code, navegue até Extensões ou pressione (Ctrl + Shift + X), no campo de pesquisa escreva "PyMakr", e instale a extensão no seu VS Code, dentro da extensão PyMakr crie um novo projeto do zero, e insira seu ESP32 para configurar...

Quando inserir seu ESP32 clique em visualizar terminal dentro da extensão PyMakr e pressione o botão Reset do seu ESP32, com isso faça o seu código no arquivo main.py, que foi gerado automaticamente na geração do novo projeto e clique no símbolo de upload para conseguir compilar e rodar o seu código no ESP32...

### Recomendação de código
Recomendo que realize o teste de funcionamento do MicroPython no seu ESP32, com o código Blink que eu deixei disponibilizado em meu [GitHub](https://github.com/DevFernandoMartins)

Link do Código Blink: https://github.com/DevFernandoMartins/ESP32-Blink
 ## Contribuindo

Contribuições são bem-vindas! Se você encontrar algum problema ou tiver sugestões para melhorias, por favor, entre em contato via instagram [@DevFernandoMartins](https://instagram.com/DevFernandoMartins)

##
#### Copyright © 2023 / [Fernando Martins](https://github.com/DevFernandoMartins)

A permissão é concedida, gratuitamente, a qualquer pessoa que obtenha uma cópia deste arquivo, sem restrição nos direitos de usar, copiar, modificar ou mesclar.