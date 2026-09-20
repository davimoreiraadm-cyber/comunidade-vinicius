# Trader Elite — site estático

## Estrutura
- `/`         home
- `/membros`  área de membros (Supabase Auth + player Bunny)
- `/quiz`     funil do quiz
- `/evento`   inscrição da Imersão
- `/admin`    painel de importação de FTD (INTERNO)
- `/termos`   termos + privacidade (placeholder)

## Publicar na Vercel
1. Crie um repositório no GitHub e suba esta pasta.
2. vercel.com > New Project > importe o repo > Deploy.
   (Framework Preset: **Other** / Output: raiz. É HTML puro, sem build.)
3. Sai no ar em `seu-projeto.vercel.app`.

## Comprar o domínio (na Vercel)
Settings > Domains > compre `traderelite.com` > ela configura o DNS sozinha.

## Depois de publicado — checklist
- [ ] Supabase > Authentication > **Site URL** = https://traderelite.com
- [ ] Bunny > Segurança > **Allowed Referrers** = traderelite.com  (só liga em produção)
- [ ] Supabase: aplicar migrations e subir as Edge Functions (importar-ftd, ir) + secrets
- [ ] Religar confirmação de e-mail no Supabase (estava desligada p/ teste)
- [ ] **Proteger /admin**: Vercel > Settings > Deployment Protection (senha),
      ou mova a pasta admin pra fora do deploy público.
- [ ] Conferir chaves em /membros/index.html (SUPABASE_URL, ANON, REDIRECT_BASE)

## Pendências de conteúdo
- Quiz e Evento estão como protótipo (captura de lead ainda a ligar no Supabase).
- Termos/Privacidade são placeholder.
