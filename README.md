# Instalação do Postman no Ubuntu 22.04

O **Postman** é uma ferramenta amplamente utilizada para desenvolvimento e testes de APIs. Neste guia, você aprenderá a instalar o **Postman Desktop** no Ubuntu 22.04 utilizando o método manual, garantindo total controle sobre a versão instalada.

<!--
https://www.youtube.com/@renato-coelho
-->

## Apresentação em Vídeo

<p align="center">
  <a href="https://youtu.be/vzWDQPcx4Lk" target="_blank"><img src="imagens/thumbnail/thumbnail-postman-ubuntu-github-01.png" alt="Vídeo de instalação do Postman no Ubuntu"></a>
</p>

![YouTube Video Views](https://img.shields.io/youtube/views/vzWDQPcx4Lk) ![YouTube Video Likes](https://img.shields.io/youtube/likes/vzWDQPcx4Lk)

## Requisitos

+ ![Ubuntu](https://img.shields.io/badge/Ubuntu-22.04-E3E3E3)
+ ![Tar](https://img.shields.io/badge/Tar-1.34-E3E3E3)
+ ![Wget](https://img.shields.io/badge/Wget-1.21.2-E3E3E3)

## Baixando e Instalando o Postman

+ **Baixe o arquivo tarball do Postman**:

```bash
wget https://dl.pstmn.io/download/latest/linux64 -O postman.tar.gz
```

Ou acesse: [https://www.postman.com/downloads/](https://www.postman.com/downloads/)

+ **Extraia o conteúdo para `/opt/`**:

```bash
sudo tar -xvf postman.tar.gz -C /opt
```

+ **Crie um link simbólico para facilitar o acesso**:

```bash
sudo ln -s /opt/Postman/Postman /usr/local/bin/postman
```

+ **Teste a instalação executando o Postman**:

```bash
postman
```

## Criando um atalho no menu de aplicativos

Para facilitar o acesso ao Postman, podemos adicionar um atalho no menu do Ubuntu.

+ **Crie um arquivo de atalho no diretório de aplicativos**:

```bash
nano ~/.local/share/applications/postman.desktop
```

+ **Adicione o seguinte conteúdo ao arquivo**:

```ini
[Desktop Entry]
Name=Postman
Exec=/opt/Postman/Postman
Icon=/opt/Postman/app/resources/app/assets/icon.png
Terminal=false
Type=Application
```

+ **Dê permissão de execução ao atalho**:

```bash
chmod +x ~/.local/share/applications/postman.desktop
```

+ **Atualize o cache de ícones do menu**:

```bash
gtk-update-icon-cache
```

Agora, o **Postman** estará disponível no menu de aplicativos do Ubuntu.

## Removendo o Postman

Caso queira remover o Postman, siga estes passos:

```bash
sudo rm -rf /opt/Postman
sudo rm /usr/local/bin/postman
rm ~/.local/share/applications/postman.desktop
```

Isso removerá o Postman completamente do sistema.


## Referências

Download Postman, **Postman**. Disponível em: <https://www.postman.com/downloads>. Acesso em: 06 fev. 2025.

Postman documentation overview, **Postman Docs**. Disponível em: <https://learning.postman.com/docs/introduction/overview/>. Acesso em: 06 fev. 2025.

Exemplo Request, **Via CEP**. Disponível em: <https://viacep.com.br/ws/01001000/json/>. Acesso em: 06 fev. 2025.
