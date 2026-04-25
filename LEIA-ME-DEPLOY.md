# LEIA-ME — Deploy do Site CBB Advogados
# ============================================================

## ESTRUTURA

```
cbb-site/
├── index.html
├── advogados.html
├── artigos.html
├── contato.html
├── style.css
├── script.js
├── netlify.toml
├── img/
│   ├── logo-horizontal-branco.png   ← Logo branca (navbar/footer)
│   ├── logo-empilhado-azul.png      ← Logo empilhada (seção por que nós)
│   └── marca-cbb-azul.png           ← Monograma CBB azul
└── artigos/
    ├── emprestimo-consignado-indevido.html
    ├── guarda-compartilhada-guia-completo.html
    └── aposentadoria-por-incapacidade-como-requerer.html
```

---

## DEPLOY NO NETLIFY

### Opção mais simples (arrasta e solta)
1. Acesse https://app.netlify.com e faça login
2. "Add new site" > "Deploy manually"
3. Comprima a pasta `cbb-site/` em um ZIP
4. Arraste o ZIP na área indicada
5. Site no ar em menos de 1 minuto

### Opção com GitHub (recomendado)
1. Crie um repositório no GitHub com os arquivos
2. No Netlify: "Import an existing project" > GitHub
3. Build settings: deixe tudo em branco (site estático)
4. Cada `git push` atualiza o site automaticamente

---

## O QUE PREENCHER ANTES DE PUBLICAR

### Obrigatório
- [ ] Substituir `5524XXXXXXXX` pelo número real do WhatsApp (com DDI+DDD, sem espaços)
- [ ] Preencher endereço, telefone e e-mail reais em todos os arquivos
- [ ] Preencher bios completas de Kenny Botelho e Matheus Borges em `advogados.html`
- [ ] Adicionar especialidades reais de Kenny e Matheus nos cards e perfis

### Recomendado
- [ ] Adicionar fotos reais dos advogados (criar `img/yohan.jpg`, `img/kenny.jpg`, `img/matheus.jpg`)
       Para usar: descomente as tags `<img>` e remova os blocos `<div class="lawyer-...-photo-mono">`
- [ ] Adicionar foto real do escritório na seção "Por que nós" em `index.html`
- [ ] Substituir depoimentos fictícios por reais (com autorização)
- [ ] Integrar iframe do Google Maps em `contato.html`
- [ ] Registrar domínio `cbbadvogados.adv.br` e configurar no Netlify

---

## FORMULÁRIO DE CONTATO (Netlify Forms — grátis)

Em `contato.html`, adicione `data-netlify="true"` ao `<form>`:
  <form id="contactForm" data-netlify="true" name="contato">

Configure o e-mail de destino em:
Netlify > Site > Forms > Form notifications

---

## FOTOS
1. Crie ou já existe a pasta `img/`
2. Adicione: `yohan.jpg`, `kenny.jpg`, `matheus.jpg` (recomendado: proporção 3:4)
3. Nos arquivos HTML, localize o comentário `<!-- Substitua por: -->` e siga as instruções

---

## GOOGLE MAPS
1. maps.google.com > busque o endereço
2. Compartilhar > Incorporar um mapa > copie o iframe
3. Em `contato.html`, substitua o bloco `.map-placeholder` pelo iframe
