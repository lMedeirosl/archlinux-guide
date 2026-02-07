Until i know each one of these i ll keep them here....
</br>

## Comandos Interessantes (basicos) 0-0

 Atualizar tudo:

```bash
sudo pacman -Syu
```


 Instalar um programa:

```bash
sudo pacman -S nome-do-pacote
```



 Procurar pacote:

```bash
pacman -Ss termo
```



 Remover um pacote:

```bash
sudo pacman -Rs nome-do-pacote
```

```bash
pkill (nome do software ou app aberto)  # fecha todas as abas abertas de um mesmo app
```

---

##  Navegar no sistema de arquivos

```bash
pwd # mostra onde vc esta
```



```bash
ls # lista arquivos/pastas
```



```bash
cd nome-da-pasta  # entra na pasta
```



```bash
cd ..  # volta uma pasta
```



---

##  Manipular arquivos/pastas

```bash
mkdir nome  # cria pastas
```



```bash
touch arquivo.txt   #  cria arquivo novo
```



```bash
cp origem destino   #  copia arquivo
```



```bash
mv origem destino # move ou renomeia
```



```bash
rm arquivo # deleta arquivos
```



```bash
rm -r pasta/  # deleta pasta inteira
```



---

##  Ver conteúdo de arquivos

```bash
cat arquivo.txt  # mostra texto dos arquivos
```



```bash
nano arquivo.txt  # abre editor de texto facil
```


---

##  Ver uso do sistema

```bash
df -h     # espaco no disco
```



```bash
du -sh pasta/    # tamanho da pasta
```



```bash
top        # Mostra apps/processos usando CPU/RAM
```



---

## My Packages
<ol>
  <li>base-devel</li>
  <li>bash</li>
  <li>discord</li>
  <li>firefox</li>
  <li>git</li>
  <li>htop (tipo gerenciador de tarefas) </li>   
  <li>btop (tipo gerenciador de tarefas 2) </li>
  <li>nano</li>
  <li>network manager</li>
  <li>obsidian</li>
  <li>polkit</li>
  <li>xdg-utils</li>
  <li>wine</li>
  <li>mesa</li>
  <li>pipewire</li>
  <li>steam</li>
  <li>pipewire-audio</li>
  <li>pipewire-alsa</li>
  <li>pipewire-pulse</li>
  <li>wireplumber</li>
 <li>wofi</li>
 <li>fastfetch (terminal famosinho) </li>   
 <li>gufw</li>
 <li>fwupd</li>
 <li>flatpak</li>
 <li>code (vs code) </li>
 <li>hyprland</li>
 <li>waybar</li>
 <li>kitty (terminal) </li>   
 <li>rofi</li>
 <li>hyprpaper</li>
 <li>ttf-jetbrains-mono-nerd</li>
 <li>wl-clipboard</li>
 <li>grim</li>
 <li>slurp</li>
 <li>telegram-desktop</li>
 <li>evince</li>
 <li>ranger (Explorador de arquivos)</li> 
 <li>neovim</li>
 <li>cava (visualizador de audio) </li>
<li>cmatrix (codigos estetica) </li>
<li>libreoffice-fresh</li>
 
</ol>


## **1. Gerenciamento de pacotes (pacman)**

No Arch Linux, o gerenciador de pacotes principal é o `pacman`. Com `sudo`, você faz:

```bash
sudo pacman -Syu       # Atualizar sistema e pacotes
sudo pacman -S nome_do_pacote  # Instalar pacote
sudo pacman -R nome_do_pacote  # Remover pacote
sudo pacman -Ss termo   # Buscar pacote nos repositórios
sudo pacman -Qi nome_do_pacote  # Informações sobre o pacote instalado
sudo pacman -Qs termo   # Buscar pacotes instalados
sudo pacman -Sy         # Atualizar lista de pacotes (sem atualizar o sistema)
```

Se você usa o **AUR**, pode usar o `yay` ou `paru` com sudo em alguns casos:

```bash
yay -S nome_do_pacote  # Instalar pacote do AUR
```

---

## **2. Gerenciamento de serviços (systemd)**

Para iniciar, parar, habilitar ou checar serviços:

```bash
sudo systemctl start nome_do_serviço      # Iniciar serviço
sudo systemctl stop nome_do_serviço       # Parar serviço
sudo systemctl restart nome_do_serviço    # Reiniciar serviço
sudo systemctl enable nome_do_serviço     # Habilitar serviço no boot
sudo systemctl disable nome_do_serviço    # Desabilitar serviço no boot
sudo systemctl status nome_do_serviço     # Ver status do serviço
sudo systemctl daemon-reload              # Recarregar serviços após alterações
```

---

## **3. Gerenciamento de usuários e permissões**

```bash
sudo useradd nome_do_usuario         # Criar usuário
sudo passwd nome_do_usuario          # Definir senha
sudo userdel -r nome_do_usuario      # Remover usuário e home
sudo groupadd nome_do_grupo          # Criar grupo
sudo gpasswd -a usuario grupo        # Adicionar usuário ao grupo
sudo chmod 755 arquivo               # Alterar permissões de arquivos
sudo chown usuario:grupo arquivo     # Alterar dono/grupo do arquivo
```

---

## **4. Gerenciamento de disco e sistemas de arquivos**

```bash
sudo fdisk -l                        # Listar partições
sudo mkfs.ext4 /dev/sdX1             # Criar sistema de arquivos
sudo mount /dev/sdX1 /mnt            # Montar partição
sudo umount /mnt                     # Desmontar partição
sudo blkid                            # Mostrar UUIDs das partições
sudo df -h                            # Espaço usado em disco
sudo fsck /dev/sdX1                   # Verificar e reparar sistema de arquivos
```

---

## **5. Rede e firewall**

```bash
sudo ip addr show                   # Mostrar interfaces de rede
sudo ip link set dev eth0 up        # Ativar interface
sudo ip link set dev eth0 down      # Desativar interface
sudo systemctl restart NetworkManager.service  # Reiniciar rede
sudo ufw enable                      # Ativar firewall (se usar ufw)
sudo ufw status                      # Ver status do firewall
sudo ufw allow 22/tcp                # Abrir porta
```

---

## **6. Atualização e manutenção do sistema**

```bash
sudo pacman -Syu                      # Atualizar tudo
sudo pacman -Sc                       # Limpar cache de pacotes antigos
sudo journalctl -xe                   # Ver logs do sistema
sudo reboot                           # Reiniciar sistema
sudo shutdown now                     # Desligar sistema
sudo dmesg                            # Ver logs do kernel
```

---

## **7. Outros comandos úteis com sudo**

```bash
sudo nano /etc/pacman.conf            # Editar arquivos de configuração
sudo vim /etc/fstab                   # Editar fstab (partições)
sudo mount -o remount,rw /            # Remontar root como leitura e escrita
sudo ln -s /origem /destino           # Criar links simbólicos
sudo tar -xvf arquivo.tar.gz -C /destino   # Extrair arquivos com permissões
```

---

**Dica:** No Arch Linux, qualquer comando que altere arquivos do sistema, serviços ou pacotes precisa de `sudo`. Comandos só para leitura, como `ls`, `cat`, `top`, não precisam.


## **1. Movimentação de janelas**

* **Super + arrastar com o botão esquerdo do mouse** → Mover a janela pela tela.
* **Super + arrastar com o botão direito do mouse** → Redimensionar a janela.

Esses são os principais “drag & drop” de janelas que você mencionou.

---

## **2. Fechar janelas**

* **Super + Q** → Fecha a janela atual. (no meu caso abre o terminal kitty , eu troquei mesmo)

---

## **3. Maximizar/minimizar**

* **Super + F** → Alterna entre maximizar/restaurar a janela (fullscreen).
* Alguns setups têm: **Super + M** → Minimizar janela (dependendo da configuração).

---

## **4. Alternar janelas e workspaces**

* **Super + Tab** → Alternar entre janelas abertas.
* **Super + [1-9]** → Mudar para o workspace 1–9.
* **Super + Shift + [1-9]** → Mover a janela atual para outro workspace.

---

## **5. Layouts e snapping**

* **Super + H / Super + L** → Ajusta janela para esquerda/direita (divisão de tela, tipo “tiling”).
* **Super + Enter** → Abrir terminal (normalmente mapeado).

---

## **6. Outros comandos úteis**

* **Super + R** → Reinicia o Hyprland (recarrega configuração).
* **Super + Esc** → Exibe menu de janelas (dependendo da configuração).
* **Super + T** → Sempre “on top” (deixar janela acima das outras).

---

 **Importante:** No Hyprland, **quase tudo é configurável** no `hyprland.conf`. Então, se você abrir `~/.config/hypr/hyprland.conf`, verá seções como:

```ini
# Window dragging/resizing
bind = SUPER, BTN_LEFT, move
bind = SUPER, BTN_RIGHT, resize

# Close window
bind = SUPER, Q, close

# Fullscreen
bind = SUPER, F, fullscreen

# Areas de trabalho
bind= SUPER,SHIFT,1-2-3-...-9  #Mandar essa janela para a area de trabalho correspondente a numeracao indicada
bind= SUPER,1-2-3-...-9  #Navegar entre diferentes areas de trabalho
```

Isso significa que você pode mudar qualquer atalho como quiser basta mudar no seu pc ai

## Outras configs interessantes:
### 1
sudo nano /etc/pacman.conf
Oq fazer ali: Tirar a # (ativar as linhas) de "color" e em "parallel downloads". E na ultima linha desse bloco adicionar : "ILoveCandy".



