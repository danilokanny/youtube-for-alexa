Bem-vindo à documentação do youtube para alexa skill por Andrewstech

Para usar essa habilidade, você deve criar uma conta aws lambda. No entanto, se você não se sentir confiante ao fazer isso, faça uma pequena doação de £ 2 ou US $ 4 e anexe seu e-mail na caixa de doações e coloque o que você deseja, então será configurado para você. https://paypal.me/andrewstechshow (observe que você receberá um aws arn por sua habilidade).

O link original foi desenvolvido por Andrew's Tech https://github.com/andrewstech/

Se você gosta deste projeto, considere doar https://paypal.me/andrewstechshow

se você tiver algum problema, poste-o o problema.
## Features
* Toque audio de YouTube videos
* Toque video (se suportado) videos ao vivo ou se você pedir apenas por um vídeo específico (command 8)
* Faça uma lista de todos os videos, no App Alexa

## Launching (iniciando)
* In English, say "Alexa, launch YouTube". 
* In German, say "Alexa, öffne YouTube". 
* In Italian, say "Alexa, avvia YouTube".
* Em Português, diga "Alexa, abrir YouTube"
* In Spanish, say "Alexa, abrir YouTube".

## Skill Commands

1. Reproduza um vídeo, por exemplo, "Alexa, peça ao YouTube para tocar Gangnam Style"
2. Reproduzir uma lista de reprodução, por exemplo "Alexa, peça ao YouTube para reproduzir a lista de reprodução Ultimate Beyonce"
3. Reproduza um canal, por exemplo, "Alexa, peça ao YouTube para reproduzir o canal Fall Out Boy Vevo"
4. Você pode substituir "play" por "shuffle" para obter uma versão aleatória dos resultados da pesquisa / canal / playlist, por exemplo, "Alexa, peça ao YouTube para alterar o canal Nicki Minaj"
5. Próximo / Anterior / Iniciar novamente / Pausar / Continuar deve funcionar
6. Pergunte o que está tocando por "Alexa, pergunte ao YouTube que música está tocando" (ou apenas "Alexa, você pode repetir isso?" Deve lhe dizer)
7. Skip forward or back in the video by "Alexa, peça para  YouTube to skip forward/backward to/by one minute and one second"
8. Basta reproduzir um vídeo de "Alexa, peça ao YouTube para reproduzir um vídeo Gangnam Style". Você pode ativar e desativar o modo "reprodução automática" com "Alexa, peça ao YouTube para ativar / desativar a reprodução automática".
9. Find the current time in the video by "Alexa, ask YouTube what is the timestamp?"
10. Se você deseja reproduzir suas próprias listas de reprodução e o recurso de pesquisa encontrar outras pessoas, envie-me um link para sua página do youtube.
11. Reproduza vídeos relacionados, de "Alexa, peça para o YouTube para reproduzir mais como esse". Este é um recurso do YouTube, não me faz entender por que ele reproduz o que é reproduzido.

O comando 7 parece não funcionar nos eco da geração 1, não faço ideia do porquê. Os comandos 8, 9, 10 e 11 estão disponíveis apenas em inglês no momento. Precisa deles no seu idioma? Envie-me um e-mail e podemos descobrir a tradução.

## Problemas conhecidos

1. Alguns vídeos simplesmente falham, não está claro o porquê, eles simplesmente o fazem. A habilidade passa para o próximo vídeo da lista de reprodução, mas isso pode significar que às vezes ela anuncia um vídeo que não toca.
2. Parece que essa habilidade só funciona em produtos Amazon Echo, não em produtos de terceiros compatíveis com Alexa. Se você conseguir que ele funcione em outro dispositivo, entre em contato.
3. Os vídeos ao vivo funcionam nos dispositivos Gen 2 em diante, não no Eco Gen 1 original.

## Instruções de instalação

1. Acesse o Alexa Console (https://developer.amazon.com/alexa/console/ask)
2. Se você não se registrou como desenvolvedor da Amazon, precisará fazê-lo. Preencha seus dados e responda "NÃO" para "Você planeja gerar receita com aplicativos cobrando por aplicativos ou vendendo itens no aplicativo" e "Você planeja gerar receita com aplicativos exibindo anúncios da Amazon Mobile Ad Network ou Mobile Associates ? "
3. Depois de fazer login na sua conta, clique em "Criar Habilidade" no lado direito.
4. Atribua um nome à sua habilidade, por exemplo, "Minha habilidade do YouTube".
5. **Importante** Defina o idioma para o seu dispositivo Echo. Se você não tiver certeza, acesse o aplicativo Alexa, vá para Configurações, Configurações do dispositivo, clique no seu dispositivo Echo e procure em Idioma. Se o seu eco estiver definido como inglês (Reino Unido), a habilidade deverá ser inglês (Reino Unido), outros tipos de inglês não funcionarão!
6. Escolha "Custom" como modelo e "Provision Your Own" como método e clique em "Create Skill". Na página do modelo, escolha "Iniciar do zero".
7. No lado esquerdo, clique em "JSON Editor".
8. Exclua tudo na caixa de texto e copie o texto de https://raw.githubusercontent.com/ndg63276/alexa-youtube/master/InteractionModel_en.json (ou use InteractionModel_fr.json, InteractionModel_it.json, InteractionModel_de.json, InteractionModel_es.json, InteractionModel_ja.json ou InteractionModel_pt-br.json para francês, italiano, alemão, espanhol, japonês ou português do Brasil.)
9. Clique em "Salvar modelo" na parte superior.
10. Clique em "Interfaces" no menu à esquerda e ative "Audio Player" e "Video App". Clique em "Salvar interfaces".
11. Clique em "Ponto final" no menu à esquerda e selecione "AWS Lambda ARN". Em "Região Padrão", coloque o ARN. Você pode obter um ARN patrocinando-me em https://paypal.me/andrewstechshow ou clicando no botão Patrocinador na parte superior desta página. (Se você quiser testar a habilidade antes de me patrocinar, coloque arn: aws: lambda: eu-west-1: 175548706300: function: YouTubeTest - mas isso só será reproduzido no estilo Gangnam.)
12. Clique em "Salvar pontos finais"
13. Clique em "Permissões", na parte inferior esquerda.
14. Ative "Listas de leitura" e "Listas de gravação".
15. Clique em "Personalizar" no menu à esquerda.
6. Clique em "Invocação" no menu à esquerda.
17. Se você quiser chamar a habilidade de algo diferente de "youtube", altere-a aqui. Clique em "Salvar modelo" se você alterar alguma coisa.
18. Clique em "Build Model". Isso levará um minuto, seja paciente. Deverá dizer se conseguiu.
19. **Importante:** Na parte superior, clique em "Teste". Onde diz "O teste está desativado para esta habilidade", altere o menu suspenso de "Desativado" para "Desenvolvimento".

## Mantendo uma lista do que você tocou

Essa habilidade pode fazer uma lista dos últimos 90 vídeos selecionados, mas você precisa conceder permissões no aplicativo Alexa:
1. Acesse o aplicativo Alexa no seu telefone. No menu, vá para "Habilidades e jogos", depois "Suas habilidades", role para a direita e clique em "Dev".
2. Clique na sua habilidade do YouTube. Você deve ver um botão marcado "Configurações", clique nele.
3. Em seguida, pressione "Gerenciar configurações" e marque as caixas "Listas de acesso de leitura" e "Listas de acesso de gravação" e pressione "Salvar configurações".
4. Diga "Alexa, inicie o YouTube", que criará a lista e, a partir de então, os vídeos serão adicionados a ela.
A lista pode ser visualizada no aplicativo Alexa, clique em Listas no menu principal.

É isso aí!

## Favorites List

If you enable list permissions as above, the skill will make a second list called "YouTube Favorites". You can use this to set shortcuts to videos you want often, or that are hard to find in search results.
Look in the lists in the Alexa app, or at alexa.amazon.com, and you will see how it works. You add an item like:

That song I like | https://youtu.be/ZyhrYis509A

## Lista de Favoritos

Se você ativar as permissões da lista como acima, a habilidade criará uma segunda lista chamada "Favoritos do YouTube". Você pode usar isso para definir atalhos para os vídeos que deseja com frequência ou que são difíceis de encontrar nos resultados de pesquisa.
Consulte as listas no aplicativo Alexa ou em alexa.amazon.com e você verá como ele funciona. Você adiciona um item como:

Essa música que eu gosto | https://www.youtube.com/watch?v=9JJgzirnXsU&t=56s (Alterado porque Barbie Girl tava foda...)

super awesome Playlist | https://www.youtube.com/watch?v=DRu60tECT9A

Então você pode simplesmente dizer "Alexa, peça para o YouTube tocar a música que eu gosto" ou "Alexa, peça para o YouTube para tocar super incrível Playlist", e deve tocar o que quer que você tenha vinculado. O | O caractere separa o nome do link (no celular pode ser difícil de encontrar, no Android, vá para a segunda página de símbolos).
Se você encontrar um vídeo / lista de reprodução / canal que você gosta e quiser adicioná-lo aos seus favoritos, basta dizer "Alexa, peça para YouTube para adicionar este vídeo / lista de reprodução / canal aos meus favoritos". Em seguida, ele aparecerá na lista, mas você provavelmente deseja editar o nome, uma vez que apenas leva o título do vídeo. No momento, a adição de favoritos está apenas em inglês. Envie-me um e-mail se quiser traduzir.

## FAQ

* ** Alexa me diz que não consegue encontrar nenhuma habilidade de vídeo suportada, o que isso significa? Alexa está tentando ser muito inteligente e não está lançando essa habilidade. Inicie sua solicitação dizendo 'Alexa, inicie o YouTube' e, quando ela disser 'Bem-vindo ao YouTube', peça o vídeo que deseja.
* ** Ela ainda diz que não consegue encontrar nenhuma habilidade em vídeo. Certifique-se de seguir a etapa 19 acima, ativando o Testing for Development.
* ** Ela ainda diz que não consegue encontrar nenhuma habilidade em vídeo! Tente usar uma palavra diferente para iniciar a habilidade. Em inglês, diga "Alexa, inicie o YouTube". Em alemão, diga "Alexa, öffne YouTube". Em italiano, diga "Alexa, avvia YouTube". Em espanhol, diga "Alexa, abra YouTube".
* ** Estou recebendo outro problema, você pode corrigi-lo? Espero que me mande um email!
* ** Se eu tentar testar no console do desenvolvedor, ele exibirá 'Diretiva não suportada. O AudioPlayer atualmente é um espaço para nome não suportado. Verifique o log do dispositivo para obter mais informações. Isso é normal, o console do desenvolvedor não reproduz áudio. Você só precisa habilitar os testes no Console do desenvolvedor e, em seguida, pode usar a habilidade no seu dispositivo Alexa.
* ** Por que mais vídeos não funcionam como vídeo? O Alexa não fornece a capacidade de enfileirar vídeos, então você só recebe um vídeo e pára. Portanto, ele só reproduz vídeos se você solicitar um vídeo específico ou se for um vídeo ao vivo.
* ** O código não estava disponível gratuitamente? Sim sim. Infelizmente, as pessoas começaram a roubar meu código, a receber crédito e a pedir doações, agora o código é privado.
