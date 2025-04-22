# site-simples-com-html-e-css

Olá pra você que escolheu esse repositório! Nessa repositório você vai enconntrar um site bem simples feito com as tecnolgias html, css esse site(website) usando html e css foi feito apenas para praticar os estudos sobre programação front-end. Espero que gostes e também aproveita e vai dar uma passeada✌ lá no canal.

## [🛠Assistir](https://www.youtube.com/watch?v=3R7QtNcwE3c)
## [⚠Me Ajude](https://www.youtube.com/channel/UCxKIsX5OXyyNWVmomuDc-LA?sub_confirmation=1)
# Preview
![Como-Criar-um-SITE-Com-HTML-e-CSS-na-prática](/Como-Criar-um-SITE-Com-HTML-e-CSS-na-prática.png)

Para criar um Script automatizado, primeiro devemos criar um arquivo comum no terminal e colocar os parametros nele
Então, deve-se usar o sudo nano com o nome script.sh para declarar que esse arquivo é um script
Depois precisamos automatizar a instalação do apache2, caso ele não esteja instalado e fazer com que ele faça o download diretamente do github e suba um site novo dentro do nosso apache
O script deve seguir os seguintes comandos:
#! /bin/bash
if [ ! -x /etc/init.d/apache2 ]; then
echo "Apache não encontrado, iniciando a instalação..."
sudo apt-get update
sudo apt-get install apache2 -y
else
echo "Você ja possui um apache instalado"
fi

sudo mkdir -p /var/www/
