configuração da aplicação feita para aplicar testes
curso no link a seguir:
https://www.udemy.com/course/rubyonrails-5x/

rodar no prompt:
yarn # instalar caso falte
bundle install

sudo apt-get update
sudo apt-get install default-jdk
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.3.0-amd64.deb
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.3.0-amd64.deb.sha512
shasum -a 512 -c elasticsearch-7.3.0-amd64.deb.sha512 
sudo dpkg -i elasticsearch-7.3.0-amd64.deb

ps -p 1
#caso systemd
sudo systemctl start elasticsearch.service
#caso init
sudo -i service elasticsearch start

sudo vim /etc/elasticsearch/elasticsearch.yml
#alterar no editor
network.host: 0.0.0.0   
cluster.initial_master_nodes: ["node-1"]
#ao final digitar :wq

sudo systemctl restart elasticsearch.service


#finalizar com
rake dev:setup
