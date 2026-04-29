# 📘 DOCUMENTAÇÃO TÉCNICA — POKÉ ARENA CARDS

**Projeto desenvolvido por:** **XRunDev**  
**Soluções em Desenvolvimento de Sistemas**  

📍 Camaçari - BA  
📧 sac@xrundev.com  

---

![Poké Arena Cards Logo](./logo.png)

# 🏗️ Arquitetura do Projeto — Poké Arena Cards

```bash
Poké-Arena-Cards/
├── public/                # Arquivos estáticos (robots.txt, manifest, etc.)
├── src/
│   ├── components/        # Componentes reutilizáveis
│   │   ├── Navbar.tsx
│   │   ├── Hero.tsx
│   │   ├── CategorySection.tsx
│   │   ├── ProductCard.tsx
│   │   ├── FeaturedProducts.tsx
│   │   ├── Footer.tsx
│   │   └── LoadingScreen.tsx
│   │
│   ├── img/               # Logos, banners, ícones e imagens
│   │   ├── logo.png
│   │   ├── hero-bg.jpg
│   │   └── products/
│   │
│   ├── pages/             # Páginas principais
│   │   ├── Home.tsx
│   │   ├── ProductsPage.tsx
│   │   ├── ProductDetails.tsx
│   │   ├── CollectionsPage.tsx
│   │   ├── RareCardsPage.tsx
│   │   ├── ContactPage.tsx
│   │   ├── PrivacyPolicy.tsx
│   │   └── TermsOfService.tsx
│   │
│   ├── data/              # Mock de dados
│   │   └── products.ts
│   │
│   ├── App.tsx            # Configuração de rotas e estrutura global
│   ├── main.tsx           # Ponto de entrada da aplicação
│   └── index.css          # Estilos globais e Tailwind
│
├── index.html             # Template HTML principal
├── package.json           # Dependências e scripts
├── tsconfig.json          # Configuração do TypeScript
└── vite.config.ts         # Configuração do Vite

# 1. 📌 Regras de Negócio

### RN01
O cliente poderá visualizar produtos sem estar logado.

### RN02
Para comprar produtos, o cliente deverá criar uma conta ou fazer login.

### RN03
O sistema deve controlar estoque em tempo real.

### RN04
Produtos sem estoque devem aparecer como **“Esgotado”**.

### RN05
O carrinho deve calcular subtotal automaticamente.

### RN06
O sistema deve calcular frete com base no CEP.

### RN07
O cliente poderá favoritar produtos.

### RN08
O cliente poderá acompanhar status do pedido.

### RN09
Pedidos podem ter os seguintes status:
- Pendente
- Pago
- Enviado
- Entregue
- Cancelado

### RN10
O administrador poderá cadastrar, editar e remover produtos.

### RN11
O administrador poderá gerenciar estoque.

### RN12
O administrador poderá visualizar relatórios de vendas.

### RN13
Cada produto deve possuir categoria e raridade.

### RN14
Cupons devem ter validade.

### RN15
O cliente pode cancelar pedido somente antes do envio.

---

# 2. ⚙️ Requisitos Funcionais

### RF01
Cadastrar usuário.

### RF02
Realizar login/logout.

### RF03
Editar perfil.

### RF04
Listar produtos.

### RF05
Filtrar produtos.

### RF06
Buscar produtos.

### RF07
Visualizar detalhes do produto.

### RF08
Adicionar ao carrinho.

### RF09
Remover do carrinho.

### RF10
Finalizar compra.

### RF11
Calcular frete.

### RF12
Favoritar produto.

### RF13
Aplicar cupom.

### RF14
Acompanhar pedido.

### RF15
Visualizar histórico de compras.

### RF16
Administrador gerenciar produtos.

### RF17
Administrador gerenciar pedidos.

### RF18
Administrador gerenciar clientes.

### RF19
Administrador gerenciar cupons.

### RF20
Administrador visualizar dashboard.

---

# 3. 🛡️ Requisitos Não Funcionais

### RNF01
O sistema deve ser responsivo.

### RNF02
Tempo de carregamento inferior a **3 segundos**.

### RNF03
Interface intuitiva e moderna.

### RNF04
Compatível com:
- Google Chrome
- Microsoft Edge
- Mozilla Firefox

### RNF05
Dados protegidos com autenticação segura.

### RNF06
Sistema escalável.

### RNF07
Disponibilidade mínima de **99%**.

### RNF08
Código modular e componentizado.

### RNF09
SEO otimizado.

### RNF10
Acessibilidade básica.

---

# 4. 🗂️ Diagrama de Entidades

## Usuário
- id
- nome
- email
- senha
- telefone
- endereço
- tipo_usuario

## Produto
- id
- nome
- descrição
- preço
- estoque
- imagem
- raridade
- categoria_id

## Categoria
- id
- nome

## Carrinho
- id
- usuario_id

## Carrinho_Item
- id
- carrinho_id
- produto_id
- quantidade

## Pedido
- id
- usuario_id
- status
- total
- data_pedido

## Pedido_Item
- id
- pedido_id
- produto_id
- quantidade
- preço

## Cupom
- id
- código
- desconto
- validade

## Wishlist
- id
- usuario_id
- produto_id

---

# 5. 👥 Casos de Uso

## Cliente
- Cadastrar conta
- Fazer login
- Visualizar produtos
- Buscar produtos
- Filtrar produtos
- Adicionar ao carrinho
- Finalizar compra
- Aplicar cupom
- Favoritar produto
- Acompanhar pedido
- Editar perfil

## Administrador
- Fazer login
- Gerenciar produtos
- Gerenciar pedidos
- Gerenciar clientes
- Gerenciar estoque
- Gerenciar cupons
- Visualizar relatórios

---

# 6. 🔄 Fluxo Principal

```text
Usuário → navega na loja  
Usuário → seleciona produto  
Usuário → adiciona ao carrinho  
Usuário → login/cadastro  
Usuário → checkout  
Usuário → pagamento  
Sistema → cria pedido  
Sistema → atualiza estoque  
Sistema → envia confirmação
