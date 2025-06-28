# 🚀 Portainer Docker Compose Setup

Este repositório contém a configuração do **Portainer** via Docker Compose. O Portainer é uma interface gráfica para gerenciamento do Docker, facilitando a visualização, controle e administração dos containers, volumes, redes e imagens.

---

## 📦 Serviços

### ✅ portainer

* **Imagem:** `portainer/portainer-ce:latest`
* **Portas expostas:**

  * `${PORTAINER_HTTP_PORT}:9000` → Interface Web (HTTP)
  * `${PORTAINER_HTTPS_PORT}:9443` → Interface Web (HTTPS)
* **Volumes:**

  * `/var/run/docker.sock:/var/run/docker.sock` → Permite ao Portainer acessar o Docker local
  * `./portainer_data:/data` → Persistência dos dados do Portainer
* **Restart Policy:** `always`

---

## 🛠️ Como usar

### 1. Clone este repositório

```bash
git clone <URL-do-repositorio>
cd <nome-da-pasta>
```

### 2. Crie o arquivo `.env`

Crie um arquivo `.env` na raiz do projeto e defina as variáveis de ambiente:

```env
PORTAINER_HTTP_PORT=9000
PORTAINER_HTTPS_PORT=9443
```

Você pode trocar as portas conforme sua necessidade.

---

### 3. Suba o ambiente

```bash
docker compose up -d
```

O Portainer estará disponível em:

* **HTTP:** [http://localhost:9000](http://localhost:9000)
* **HTTPS:** [https://localhost:9443](https://localhost:9443)

---

### 4. Acesse o Portainer

* Ao acessar pela primeira vez, você deverá criar um usuário administrador.
* Após o login, poderá gerenciar o Docker local diretamente pela interface do Portainer.

---

## 🗑️ Para parar e remover os containers

```bash
docker compose down
```

---

## 📂 Estrutura de pastas

```
.
├── docker-compose.yml
├── portainer_data/   # Dados persistentes do Portainer
└── .env              # Variáveis de ambiente
```

---

## ℹ️ Requisitos

* [Docker](https://docs.docker.com/get-docker/)
* [Docker Compose](https://docs.docker.com/compose/)

---

## 🔒 Segurança

* Recomenda-se configurar senha forte para o usuário administrador.
* Em produção, use HTTPS para acessar o Portainer de forma segura.
* Limite o acesso às portas expostas somente a redes seguras ou utilize firewall.

---

## 📄 Referências

* [Portainer Documentation](https://docs.portainer.io/start/install/server/docker/linux)

