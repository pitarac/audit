

### **1. Verificação em Sistemas Windows:**

- **Verificar Programas Instalados:**
  Use o Painel de Controle para verificar os programas instalados. Para detalhes mais técnicos, utilize o PowerShell ou o Prompt de Comando.

  ```powershell
  Get-ItemProperty HKLM:\Software\Microsoft\Windows\CurrentVersion\Uninstall\* | Select-Object DisplayName, InstallDate
  ```
  
  Isso vai listar os programas instalados e as datas.

- **Analisar Logs do Event Viewer:**
  Abra o Event Viewer (Visualizador de Eventos) e navegue até:
  
  `Windows Logs > Application` e `Windows Logs > System`.
  
  Procure por eventos de instalação e desinstalação, geralmente identificados como "MsiInstaller" ou registros de erro.

- **Verificar Logs de Instalação do Windows:**
  Os logs de instalação ficam localizados em:
  
  `C:\Windows\inf\setupapi.dev.log` e `C:\Windows\inf\setupapi.app.log`.

### **2. Verificação em Sistemas Linux:**

- **Usar Logs do Sistema:**
  Nos sistemas Linux, os logs de instalação de pacotes podem ser verificados usando o comando `grep` nos logs do sistema.

  ```bash
  grep -i "install" /var/log/dpkg.log
  grep -i "install" /var/log/yum.log
  ```

- **Consultar Gerenciadores de Pacotes:**
  Para verificar pacotes instalados recentemente:

  - **Debian/Ubuntu:**
    ```bash
    dpkg --list | grep [nome do software]
    ```
  
  - **CentOS/Fedora:**
    ```bash
    rpm -qa | grep [nome do software]
    ```

### **3. Verificação em Sistemas MacOS:**

- **Verificar Logs do Sistema:**
  Use o Console (Aplicativo de Logs) para visualizar registros de instalação.

- **Consultar Histórico de Pacotes:**
  Verifique usando o comando `pkgutil`:
  
  ```bash
  pkgutil --pkgs
  ```

- **Verificar Diretórios de Aplicações:**
  Veja a pasta `/Applications` e `~/Applications` para verificar softwares instalados.

### **4. Softwares Específicos para Auditoria:**

- Use ferramentas como **Belarc Advisor**, **CCleaner**, ou **Sysinternals Suite** para coletar informações detalhadas sobre softwares instalados e desinstalados.


