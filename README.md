# PORTARIA FINAL - PWA

App de portaria com:
- Foto da nota (topo, só câmera)
- OCR: extrai descrição do parceiro e nº da nota
- Sync Supabase (tabela public.veiculos + bucket public veiculos-fotos)
- Voz TTS com regra pátio não informa portaria
- PWA instalável

## Deploy no GitHub Pages

1. Crie repositório no GitHub (ex: portaria-final)
2. Faça upload de todos os arquivos desta pasta na branch main / root
3. Vá em Settings > Pages > Source: Deploy from a branch > main / root
4. Ative HTTPS (obrigatório para PWA e câmera)
5. Acesse https://seuusuario.github.io/portaria-final/

## Configuração Supabase obrigatória

No SQL Editor:
```sql
drop table if exists public.veiculos;
create table public.veiculos (
  id bigint primary key,
  placa text, motorista text, frota text,
  local_descarga text, local_carro text, parceiro text,
  status text, foto_nota text, foto_placa text, foto_doc text,
  texto_voz_entrada text, texto_voz_liberacao text,
  data_entrada timestamptz, data_liberacao timestamptz,
  dados_completo jsonb, criado_em timestamptz default now()
);
alter table public.veiculos disable row level security;
```

No Storage: New bucket `veiculos-fotos` Public = YES

No app: Configurações > SUPABASE URL = https://xxx.supabase.co (sem /rest/v1) > TABELA = veiculos > KEY = anon

O botão "Criar bucket veiculos-fotos automaticamente" dentro do app também cria.

## PWA
- manifest.json + sw.js já configurados
- Instalável no Android: Abrir no Chrome > Adicionar à tela inicial
