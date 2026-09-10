# AL Revestimentos Exclusivos — landing

Landing estática (HTML/CSS/JS puro) para a AL Revestimentos Exclusivos: pedras naturais
para projetos de alto padrão. Base branca minimalista, acento dourado da marca, uma seção
e o rodapé em preto, botões de WhatsApp verdes por seção.

## Stack
- HTML + CSS inline + JS vanilla. Sem build. Deploy Vercel (estático).
- Fontes self-hosted (Fraunces display + Manrope corpo, variáveis woff2).
- Imagens WebP otimizadas em `assets/img/`.
- Logo: monograma "AL" dourado extraído (fundo transparente) em `assets/img/al-mark.png`.

## Contato (confirmado pelo cliente em 20/08/2026)
- WhatsApp: **(54) 99202-0312** → `WHATS = '5554992020312'` no `<script>` do `index.html`.
- Endereço: **R. Quintino Biazus, 193, Santa Lúcia, Caxias do Sul, RS**. O rodapé antes dizia
  Santa Catarina, que estava errado: a empresa é do Rio Grande do Sul.
- Nomes das linhas conferidos com o cliente: Pedra Moledo Black, Pedra Moledo,
  Travertino Rock Face, Fachadas em pedra, Áreas externas & pisos.

## Deploy
Repo público no GitHub + conectar na Vercel (auto-deploy no push da main).

### O endereço da Vercel não vai para o Google
`alrevestimentos.vercel.app` responde com `X-Robots-Tag: noindex, nofollow`.
A regra no `vercel.json` tem um `has` de host, então vale **só** nesse
endereço: no dia em que o domínio próprio do cliente entrar, ele indexa
normalmente sem precisar mexer em nada. Isso é de propósito — um `noindex`
solto no repositório é o tipo de coisa que ninguém lembra de tirar e que
mantém o site oficial fora da busca por meses.

O `robots.txt` **libera** o rastreamento, e isso também é de propósito: para
o Google tirar uma página do índice ele precisa entrar e ler o `noindex`.
Bloquear no `robots.txt` faz o oposto — a URL fica no índice, só que sem
resumo, e não sai mais.

Se a URL já estiver na busca, o `noindex` sozinho leva semanas. Para tirar em
um ou dois dias, pedir pela ferramenta pública do Google, que não exige ter o
domínio verificado:
<https://search.google.com/search-console/remove-outdated-content>

### Se o endereço da Vercel voltar a dar 404
Foi o *deployment* que sumiu, não o projeto: o projeto `alrevestimentos`
continua na conta e o apelido `alrevestimentos.vercel.app` continua reservado,
só que sem nada por trás. Basta um push na `main` para a Vercel construir de
novo e o endereço voltar.

Apagar o deployment não tira nada do Google, e ainda piora: o resultado
continua na busca por semanas e quem clica cai numa tela de erro da Vercel em
vez do site.
