# Comatizar a instalação do Apache2 e subir um Site

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

sudo mkdir -p /var/www/aluno/public_html
cd /var/www/alunos/public_html
sudo git clone https://github.com/matheusmanuel/site-simples-com-html-e-css-.git
sudo cp -r site-simples-com-html-e-css-/
cd /etc/apache2/sites-available/
sudo tee aluno.conf<<EOF
<VirtualHost *:80>
        ServerAdmin admin@site1
        ServerName site1
        serverAlias www.site1
        DocumentRoot /var/www/site1/public_html
        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
<VirtualHost>
EOF

sudo a2ensite aluno.conf

sudo echo "127.0.0.1   aluno" | sudo tee -a /etc/hosts

sudo /etc/init.d/apache2 restart
sudo /etc/init.d/apache2 status



