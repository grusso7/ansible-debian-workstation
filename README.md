# 🐧 Debian Workstation - Ansible Setup

![Ansible](https://img.shields.io/badge/ansible-%231A1918.svg?style=for-the-badge&logo=ansible&logoColor=white)
![Debian](https://img.shields.io/badge/Debian-D70A53?style=for-the-badge&logo=debian&logoColor=white)
![GNOME](https://img.shields.io/badge/GNOME-4A86CF?style=for-the-badge&logo=gnome&logoColor=white)
![Zsh](https://img.shields.io/badge/Zsh-111D32?style=for-the-badge&logo=zsh&logoColor=white)

Questo repository contiene playbook e ruoli [Ansible](https://www.ansible.com/) volti all'automazione post-installazione per ottenere una workstation operativa su base **Debian (testing/sid)**. 

Con un solo comando, il sistema andrà ad autoconfigurare:
- 📦 **Strumenti base e CLI**: Git, Lazygit, Ripgrep, fd-find, htop.
- 🐚 **Shell Moderno**: ZSH configurato con plugin nativi apt (`autosuggestions` e `syntax-highlighting`).
- 💻 **Ambiente di Sviluppo**: Editor Neovim con bootstrap alla configurazione **LazyVim**.
- 🛠️ **Esperienza Desktop (GNOME)**: Ptyxis terminal, cursori Bibata Modern Classic, estensioni Dash-to-Dock, Blur My Shell, temi e font *UbuntuMono Nerd Font*.

## 🚀 Come usarlo (Quickstart)

1. Assicurati che Ansible e git siano installati sulla tua macchina:
   ```bash
   sudo apt update && sudo apt install git ansible -y
   ```
2. Clona questo repository e accedi alla cartella:
   ```bash
   git clone git@github.com:grusso7/ansible-debian-workstation.git
   cd ansible-debian-workstation
   ```
3. Lancia il playbook principale:
   ```bash
   ansible-playbook -i inventory.ini site.yml -K
   ```
   *(La flag `-K` serve per far chiedere ad Ansible la password di admin, necessaria per i permessi apt e dconf sys-wide).*

## 📚 Documentazione approfondita

Per capire a fondo come è strutturato il codice sotto cofano, quali sono le directory rilevanti (es. `roles/`) e come estendere questo ecosistema, consulta il:

👉 **[Manuale Completo del Repository (docs/manuale.md)](docs/manuale.md)**

## 🛡️ Idempotenza 

Il progetto è scritto pensando all'**idempotenza**. Ciò significa che puoi rieseguire il comando quante volte desideri: Ansible applicherà le modifiche unicamente dove la tua macchina non è conforme allo stato descritto, risparmiando tempo sulle configurazioni già effettuate!

---

> Progetto rilasciato liberamente sotto licenza Open Source. Prendine spunto e crea la macchina perfetta per le tue esigenze!
