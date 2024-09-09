# Configuração do Debian para UFW

Este passo a passo é para auxiliar na configuração do Debian para ter mais controle na rede e usar apenas as portas necessárias. É importante ser cauteloso sempre!

## Passo 01: Instalação do UFW

Instale o `UFW` (Uncomplicated Firewall) com o seguinte comando:

```bash
sudo apt install ufw
```

## Passo 02: Fechar todas as portas (entrada e saída)

Configure o `UFW` para negar todas as conexões de entrada e saída por padrão:

```bash
sudo ufw default deny incoming
sudo ufw default deny outgoing
```

## Passo 03: Abrir portas específicas

Permita o tráfego nas portas necessárias:

- **Porta 53 (DNS):**

  ```bash
  sudo ufw allow 53
  ```

- **Porta 80 (HTTP):(opcional)**

  ```bash
  sudo ufw allow 80/tcp
  ```

- **Porta 443 (HTTPS):**

  ```bash
  sudo ufw allow 443/tcp
  ```

## Passo 04: Habilitar o UFW

Ative o `UFW` para aplicar as configurações:

```bash
sudo ufw enable
```

## Passo 05: Verificar o status do UFW

Verifique o status do `UFW` para confirmar as regras aplicadas:

```bash
sudo ufw status
```

Com esses passos, você configurará o Debian para permitir apenas o tráfego nas portas 53 (DNS), 80 (HTTP) e 443 (HTTPS), bloqueando todas as outras portas.