<div align="center">
  <h1><font color="#0056b3">🌐 Infraestrutura de Redes: Servidor Ubuntu 24.04</font></h1>
  
  <p><b>Projeto de Implementação de Arquitetura Cliente-Servidor</b></p>

  <img src="https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white">
  <img src="https://img.shields.io/badge/Apache-D22128?style=for-the-badge&logo=Apache&logoColor=white">
  <img src="https://img.shields.io/badge/OpenSSH-000000?style=for-the-badge&logo=openssh&logoColor=white">
  <img src="https://img.shields.io/badge/VirtualBox-214294?style=for-the-badge&logo=VirtualBox&logoColor=white">
</div>

<hr>

## 📝 Visão Geral
Este projeto documenta a configuração de uma máquina virtual (Ubuntu) atuando como **Servidor** para uma máquina física (Windows) atuando como **Cliente**. A comunicação foi estabelecida via meio de transmissão cabeado virtual através do **VirtualBox**.

## ⚙️ Configuração da VM (UBUNTU-ARI)
Para garantir a estabilidade do sistema e evitar falhas de instrução de memória, as especificações utilizadas foram:
* **Memória RAM:** 4096 MB (4GB)
* **Memória de Vídeo (VRAM):** 128 MB
* **Rede:** Modo NAT com Encaminhamento de Portas

<div align="center">
  <img src="https://github.com/user-attachments/assets/1a2b9ca6-1408-4250-9d0a-e759067a7e6a" width="85%" alt="Configuração da VM">
</div>
<div align="center">
<img width="642" height="392" alt="image" src="https://github.com/user-attachments/assets/c80eae02-93c3-4cea-9fbf-ddd1c4f58f57" />



### 🚀 Mapeamento de Portas (Port Forwarding)
<table align="center">
  <tr>
    <th>Serviço</th>
    <th>Porta Host (Windows)</th>
    <th>Porta Guest (Ubuntu)</th>
  </tr>
  <tr>
    <td><b>HTTP (Web)</b></td>
    <td><code>8080</code></td>
    <td><code>80</code></td>
  </tr>
  <tr>
    <td><b>SSH (Remoto)</b></td>
    <td><code>2222</code></td>
    <td><code>22</code></td>
  </tr>
  <tr>
    <td><b>FTP (Arquivos)</b></td>
    <td><code>2121</code></td>
    <td><code>21</code></td>
  </tr>
</table>

---

## 🛠️ Serviços Instalados
1. **Apache2:** Servidor HTTP para hospedagem de páginas web.
2. **OpenSSH:** Servidor para acesso e controle remoto via terminal.
3. **Vsftpd:** Servidor para transferência de arquivos.
4. **UFW (Firewall):** Habilitado e configurado para liberar as portas 80, 22 e 21.

<div align="center">
  <img src="https://github.com/user-attachments/assets/1a2b9ca6-1408-4250-9d0a-e759067a7e6a" width="85%" alt="Configuração da VM">
</div>

   

---

## 🔍 Diagnóstico e Resolução de Problemas
Um ponto crítico da atividade foi a resolução de conflitos de rede:
* **Problema:** O protocolo FTP convencional (porta 2121) apresentou *time-out* na listagem de diretórios devido a restrições do NAT.
* **Solução:** Utilização do protocolo **SFTP** via porta 2222, estabelecendo a comunicação através de um túnel SSH seguro.

---

## 📊 Validação dos Testes

<div align="center">
  <h3>1. Servidor Web Ativo (Apache)</h3>
  <p>Acesso via navegador no host (Windows) através da porta 8080.</p>
  <img src="./img/print_navegador.png" width="85%" alt="Print do Servidor Web">

  <br><br>

  <h3>2. Conexão SSH via Terminal</h3>
  <p>Validação do acesso remoto seguro via prompt de comando.</p>
  <img src="./img/print_ssh.png" width="85%" alt="Print do Acesso SSH">

  <br><br>

  <h3>3. Transferência de Arquivos (SFTP)</h3>
  <p>Configuração do Gerenciador de Sites no FileZilla para contornar limitações do NAT.</p>
  <img src="./img/print_filezilla.png" width="85%" alt="Print do FileZilla">
</div>

<hr>

<div align="center">
  <p><i>Atividade concluída com sucesso e ambiente totalmente funcional.</i></p>
</div>
