# Treinix

Organizador de treinos. O app inteiro é a pasta `www/` (um `index.html` com manifesto, service worker e ícones).

Há dois caminhos, e dá para usar os dois ao mesmo tempo. Ambos usam o GitHub, que é gratuito.

## Caminho A: site instalável (PWA), funciona offline

1. Crie uma conta em github.com e um repositório novo (por exemplo, `treinix`).
2. Envie todo o conteúdo desta pasta para o repositório (botão **Add file > Upload files**, arrastando tudo, inclusive a pasta `.github`).
3. No repositório, abra **Settings > Pages** e, em **Source**, escolha **GitHub Actions**.
4. Aguarde 1 a 2 minutos. Na aba **Actions** o fluxo "Publicar site (PWA)" fica verde, e o endereço aparece em **Settings > Pages**, algo como `https://seu-usuario.github.io/treinix/`.
5. Abra o endereço no celular:
   - **Android (Chrome):** menu ⋮ > **Instalar app**.
   - **iPhone (Safari):** botão compartilhar > **Adicionar à Tela de Início**.
6. Depois da primeira abertura com internet, o app abre também sem internet.

Para publicar uma nova versão: substitua `www/index.html`, aumente o número em `CACHE` no arquivo `www/sw.js` (por exemplo, `treinix-v2`) e envie de novo.

## Caminho B: APK para Android (sem instalar nada no computador)

1. Com o repositório criado como acima, abra a aba **Actions**.
2. Escolha **Gerar APK** e clique em **Run workflow**.
3. Espere uns 5 a 10 minutos. Ao terminar, abra a execução e baixe o arquivo **treinix-apk** (um .zip com o `app-debug.apk` dentro).
4. Passe o `.apk` para o celular, abra-o e permita a instalação de apps de fontes desconhecidas quando o Android pedir.

Esse APK é de teste (debug): serve para uso pessoal e para instalar direto no seu aparelho, mas não para a Play Store. Para publicar na loja seria preciso gerar uma versão assinada.

## Observações

- Treinos, fotos e vídeos enviados ficam guardados no aparelho. Cada aparelho (e cada navegador) tem os seus dados. Para levar treinos de um aparelho para outro, use a exportação e a importação na aba Perfil. Fotos e vídeos não entram na exportação.
- Vídeos do YouTube incorporados podem não tocar dentro do APK. O botão **Abrir link** sempre funciona.
- Se o fluxo do APK falhar, abra a execução com erro e copie a mensagem da etapa em vermelho. Com ela é fácil corrigir.
