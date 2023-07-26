# Realtek RTL8811CU for Ubuntu 22.04
Driver Realtek RTL8811CU para Linux Ubuntu
Testado no kernel 5.19.0-50
<br>
Se você está usando tradutor nesta página, poderá encontrar erros nos comandos <br>
recomendo acessar o <a href="https://meuip.tk">site</a> para códigos mais precisos

VERIFIQUE SE EXISTE ALGUM DRIVER INSTALADO COM O COMANDO
<code>sudo dkms status</code>______________________________<br><br>

SE APARECEER ALGUM DRIVER SEGUDO DE "installed" <br>
POR EXEMPLO: <br>
<span>rtl8821bu/5.12.0.4, 5.19.0-50-generic, x86_64: installed</span> <br>
VOCÊ DEVE REMOVER PARA NÃO DAR CONFLITOS <br>
DIGITE: <br>
<pre>sudo dkms remove rtl88x2bu/5.12.0.4 --all</pre>______________________________<br><br>

SUBSTITUA PELO DRIVER QUE APARECE NO SEU TERMINAL <br>


VERIFIQUE O ID DO DRIVER
<pre>lsusb</pre>

procure se alguma linha corresponde a isto <br>
<span>Bus 001 Device 002: ID 0bda:c811 Realtek Semiconductor Corp. 802.11ac NIC</span> <br>

Caso apareça um id diferente, pode não funcionar  ______________________________<br><br>

  
    
ATUALIZE OS PACOTES DO SISTEMA
<pre>sudo apt update && sudo apt upgrade</pre>______________________________<br><br>


PACOTES NECESSÁRIOS
<pre>sudo apt install -y build-essential dkms git iw</pre>______________________________<br><br>


CRIA O DIRETÓRIO PARA ARMAZENAR O DRIVER E NAVEGA ATÉ O DIRETÓRIO
<pre>mkdir -p ~/src ; cd src</pre>______________________________<br><br>


BAIXA O DRIVER
<pre>git clone https://github.com/morrownr/8821cu-20210916.git</pre>______________________________<br><br>


ABRE O DIRETÓRIO DO DRIVER
<pre>cd ~/src/8821cu-20210916</pre>______________________________<br><br>



<span>ATENÇÃO ESTE SCRIPT VAI SOLICITAR REINICIAR O COMPUTADOR</span><br>
EXECUTA O SCRIPT DE INSTALAÇÃO
VOCÊ PODE PULAR A REINICIALIZAÇÃO, MAS RECOMENDA-SE REINICIAR
<pre>sudo ./install-driver.sh</pre> ______________________________<br><br>


AO EXECUTAR O SCRIPT DE INSTALAÇÃO VAI CARREGAR O ARQUIVO DE CONFIGURAÇÃAO DO DRIVER NO EDITOR NANO, BASTA DIGITAR "ctrl+x" E DEPOIS "enter"<br>
CONFIRMAR O REINÍCIO DO COMPUTADOR COM "y" QUANDO SOLICITADO <br><br>APÓS O REINÍCIO VERIFIQUE SE O WI-FI DO COMPUTADOR ETSTÁ ATIVO <br>______________________________<br><br>

<br><br>
<span>INSTALAÇÃO MANUAL</span> <br>
SIGA OS COMANDO ABAIXO SE NÃO QUISER EXECUTAR O SCRIPT

<pre>make clean</pre>
<pre>make</pre>
<pre>sudo make install</pre>

ESPERE OS PROCESSOS TERMINAREM E REINICIE O COMPUTADOR E VERIFIQUE SE O WI-FI DO COMPUTADOR ASTÁ ATIVO<br>______________________________<br><br>
<br><br>

<span>REMOVENDO O DRIVER</span><br>


PARA REMOVER O DRIVER NAVEGUE ATÉ A PASTA DO DRIVER
<pre>cd ~/src/8821cu-20210916</pre>
<pre>sudo make uninstall</pre>



REINICIE O COMPUTADOR

</div>

<p>
    CRÉDITOS: <a href="https://github.com/morrownr/8821cu-20210916">morrownr</a>
</p>
