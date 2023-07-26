# RealtekRTL8811CU
Driver Realtek RTL8811CU para Linux Ubuntu
Testado no kernel 5.19.0-50

#VERIFIQUE SE EXISTE ALGUM DRIVER INSTALADO COM O COMANDO
sudo dkms status

SE APARECEER ALGUM DRIVER SEGUDO DE "installed"
POR EXEMPLO:
rtl8821bu/5.12.0.4, 5.19.0-50-generic, x86_64: installed
VOCÊ DEVE REMOVER PARA NÃO DAR CONFLITOS
DIGITE:
sudo dkms remove rtl88x2bu/5.12.0.4 --all
SUBSTITUA PELO DRIVER QUE APARECE NO SEU TERMINAL


#VERIFIQUE O ID DO DRIVER
lsusb

procure se alguma linha corresponde a isto
Bus 001 Device 002: ID 0bda:c811 Realtek Semiconductor Corp. 802.11ac NIC

Caso apareça um id diferente, pode não funcionar


#ATUALIZAR OS PACOTES DO SISTEMA
sudo apt update && sudo apt upgrade


#PACOTES NECESSÁRIOS
sudo apt install -y build-essential dkms git iw


#CRIA O DIRETÓRIO PARA ARMAZENAR O DRIVER E NAVEGA ATÉ O DIRETÓRIO
mkdir -p ~/src ; cd src


#BAIXA O DRIVER
git clone https://github.com/morrownr/8821cu-20210916.git


#ABRE O DIRETÓRIO DO DRIVER
cd ~/src/8821cu-20210916


#ATENÇÃO ESTE SCRIPT VAI SOLICITAR REINICIAR O COMPUTADOR
#EXECUTA O SCRIPT DE INSTALAÇÃO
#VOCÊ PODE PULAR A REINICIALIZAÇÃO, MAS RECOMENDA-SE REINICIAR
sudo ./install-driver.sh

#AO EXECUTAR O SCRIPT DE INSTALAÇÃO VAI CARREGAR O ARQUIVO DE CONFIGURAÇÃAO DO DRIVER NO EDITOR NANO, BASTA DIGITAR "ctrl+x" E DEPOIS "enter"

#CONFIRMAR O REINÍCIO DO COMPUTADOR COM "y" QUANDO SOLICITADO


#########################################################################
#INSTALAÇÃO MANUAL
#SIGA OS COMANDO ABAIXO SE NÃO QUISER EXECUTAR O SCRIPT

make clean

make

sudo make install

#ESPERE OS PROCESSOS TERMINAREM E REINICIE O COMPUTADOR


#PARA REMOVER O DRIVER NAVEGUE ATÉ A PASTA DO DRIVER
cd ~/src/8821cu-20210916
sudo make uninstall

#REINICIA O COMPUTADOR
sudo reboot


CRÉDITOS: morrownr
Github do autor: https://github.com/morrownr/8821cu-20210916
