<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/lume-store-org/lume-front/main/docs/logo-dark.svg" />
    <img src="https://raw.githubusercontent.com/lume-store-org/lume-front/main/docs/logo.svg" alt="Lume Store" width="260" />
  </picture>
</p>

<p align="center">
  <b>Tecnologia que acompanha o seu ritmo.</b><br>
  Loja online de tecnologia e estilo, construída em microserviços.
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/lume-store-org/lume-front/main/docs/demo.webp" alt="Lume Store rodando: vitrine, carrinho, checkout, meus pedidos e painel admin" />
</p>

<p align="center">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=nextjs,react,ts,tailwind,python,flask,mysql,docker" alt="Stacks" />
  </a>
</p>

## O que é

A **Lume Store** vende smartphones, notebooks, áudio, acessórios e moda. Por trás da loja, cada parte do negócio é um **microserviço independente com o seu próprio banco**, e todas as chamadas passam por um **API Gateway** que cuida da autenticação.

| Recurso | Como funciona |
|---|---|
| 🛍️ Loja completa | Vitrine, busca, categorias, carrinho, checkout e histórico de pedidos |
| 🔐 Login seguro | Senhas com scrypt e salt; sessão validada no gateway |
| 📦 Estoque em tempo real | Reservado numa transação ao fechar o pedido, devolvido no cancelamento |
| 💰 Preço confiável | Sempre do catálogo, nunca do navegador |
| 🧑‍💼 Painel admin | Indicadores, gestão de produtos e status dos pedidos |
| 📖 API documentada | Swagger em `/docs` |

## Arquitetura

<p align="center">
  <img src="https://raw.githubusercontent.com/lume-store-org/lume-infra/main/docs/arch.gif" alt="Arquitetura da Lume Store" />
</p>

## Repositórios

| Repositório | Camada | Stack |
|---|---|---|
| [lume-front](https://github.com/lume-store-org/lume-front) | Loja | Next.js 14, React, TypeScript, Tailwind |
| [lume-gateway](https://github.com/lume-store-org/lume-gateway) | API Gateway | Flask, autenticação, CORS, Swagger |
| [lume-users](https://github.com/lume-store-org/lume-users) | Usuários | Flask, MySQL |
| [lume-catalog](https://github.com/lume-store-org/lume-catalog) | Catálogo e estoque | Flask, MySQL |
| [lume-orders](https://github.com/lume-store-org/lume-orders) | Pedidos | Flask, MySQL |
| [lume-infra](https://github.com/lume-store-org/lume-infra) | Infraestrutura | Docker Compose |

## Como rodar

```bash
for r in front gateway users catalog orders infra; do git clone https://github.com/lume-store-org/lume-$r; done
cd lume-infra && cp .env.example .env && docker compose up -d --build
```

Loja em **http://localhost:3000** e API em **http://localhost:5000/docs**.

## Autor

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/willtechdev">
        <img src="https://github.com/willtechdev.png" width="100px;" alt="William Coelho"/><br>
        <sub><b>William Coelho</b></sub>
      </a>
    </td>
  </tr>
</table>
