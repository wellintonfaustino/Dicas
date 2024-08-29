## **_Conexão remota RDP com Gnome_**

Para desinstalar o XRDP e limpar qualquer configuração relacionada, e depois configurar apenas o ambiente de desktop GNOME, siga os passos abaixo.

### Passo a Passo para Desinstalar o XRDP e Reinstalar o GNOME

#### Passo 1: Desinstalar o XRDP e Remover Configurações

1. **Desinstale o XRDP e suas dependências:**

   ```bash
   sudo apt purge xrdp -y
   ```

2. **Remova pacotes e dependências órfãs:**

   ```bash
   sudo apt autoremove --purge -y
   sudo apt autoclean
   ```

3. **Remova os arquivos de configuração do XRDP:**

   ```bash
   sudo rm -rf /etc/xrdp
   sudo rm -rf /etc/polkit-1/localauthority/50-local.d/46-xrdp-nopasswd.pkla
   ```

#### Passo 2: Reinstalar o GNOME

1. **Atualize o sistema:**

   ```bash
   sudo apt update
   ```

2. **Reinstale o ambiente de desktop GNOME:**

   Se você quiser instalar a versão padrão do GNOME para Ubuntu, use:

   ```bash
   sudo apt install ubuntu-gnome-desktop -y
   ```

   Isso instalará o GNOME com todos os pacotes e dependências necessárias para uma experiência completa.

3. **Confirme se o GNOME foi instalado corretamente:**

   Verifique se o GNOME está configurado como o ambiente de desktop padrão:

   ```bash
   sudo update-alternatives --config x-session-manager
   ```

   Certifique-se de que a opção `gnome-session` esteja selecionada.

#### Passo 3: Reiniciar o Sistema

Após a instalação, reinicie o sistema para aplicar as mudanças:

```bash
sudo reboot
```

#### Passo 4: Verificar o Ambiente de Desktop GNOME

Depois de reiniciar, o GNOME deve estar configurado como o ambiente de desktop padrão. Faça login para confirmar que tudo está funcionando corretamente.

### Próximos Passos

- **Verifique o Ambiente de Desktop:** Após o login, verifique se todos os aplicativos e componentes do GNOME estão funcionando conforme esperado.
- **Configurações Adicionais:** Você pode ajustar as configurações do GNOME usando o aplicativo de "Configurações" para personalizar o ambiente de acordo com suas preferências.
