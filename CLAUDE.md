# CLAUDE.md

Site da comunidade **Trader Elite**, dos traders Caio, Lucas e Raúlzito.

## Stack
- **Frontend:** HTML estático (sem build), versionado no GitHub.
- **Deploy:** automático na Vercel a cada push na `main` (`vercel.json` com `cleanUrls: true`).
- **Backend:** Supabase
  - Auth (login/cadastro da área de membros)
  - Tabelas: `profiles`, `ftd_events`, `broker_clicks`
- **Vídeos:** Bunny Stream, library `757651`, com **Allowed Referrers** ativo (o player só carrega nos domínios liberados).
- **Tráfego:** Meta Pixel + Conversions API (CAPI).

## Páginas
| Rota | Arquivo | Descrição |
|---|---|---|
| `/` | `index.html` | Home / landing da comunidade |
| `/membros` | `membros/index.html` | Área de membros: login Supabase + player Bunny |
| `/quiz` | `quiz/index.html` | Funil de quiz (perfil do trader) |
| `/evento` | `evento/index.html` | Inscrição na Imersão |
| `/termos` | `termos/index.html` | Política de Privacidade + Termos de Uso |
| `/admin` | `admin/index.html` | Importação de FTD (relatório da Hantec). **Uso interno.** |

## Regras
- As imagens ficam **embutidas em base64** dentro do HTML. Não trocar por arquivos externos.
- Ao editar, manter os links internos como **rotas** (`/membros`, `/quiz`, `/evento`…), nunca `membros/index.html` ou `.html`.
- **Nunca commitar a `service_role` key do Supabase.** No frontend só pode ir a `anon` key; a `service_role` fica apenas nos secrets das Edge Functions.

## Pendências
- [ ] Subir as Edge Functions: redirect para a Hantec e `importar-ftd`.
- [ ] Ligar o quiz e o evento ao banco (captura de lead no Supabase).
- [ ] Colocar o logo da Trader Elite no header.
- [ ] Configurar o domínio próprio.
