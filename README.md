# Portaria PWA

## Publicar no GitHub Pages

1. Crie um repositório no GitHub.
2. Envie **todo o conteúdo desta pasta** para a raiz do repositório.
3. Em **Settings → Pages**, selecione **Deploy from a branch** e a branch `main` (ou `master`) com a pasta `/root`.
4. Abra a URL HTTPS gerada pelo GitHub Pages no celular.
5. Use a opção do navegador **Adicionar à tela inicial / Instalar aplicativo**.

## Importante para sincronização

Os aparelhos precisam estar configurados com o mesmo projeto Supabase, a mesma ANON KEY e a tabela `veiculos`.

Depois de publicar, teste em dois aparelhos:
- Testar Conexão Supabase
- Sincronizar agora
- Testar sync: criar cartão fake

## Observação

O PWA pode abrir a interface offline, mas a sincronização entre aparelhos depende de acesso à internet e ao Supabase.
