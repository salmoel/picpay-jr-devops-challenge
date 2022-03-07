## PICPAY CHALLENGE DEVOPS JR

#### DESCRIÇÃO E LÓGICA APLICADA

##### LÓGICA UTILIZADA PARA SOLUÇÃO DO DESÁFIO

<p align="justify">Bem, o primeiro passo estratégico que dei foi executar o Docker Composer e também análisar algumas outras coisas como estrutura do projeto, as informações contidas no README.md, os códigos e a lógica contida em cada um deles e, também verifiquei os logs. Fazendo esses passos conseguir análiser os erros que apareceram e depois disso comecei a pensar em soluções para eles.</p>

##### ETAPAS
###### - BUILD COMPOSE

<p align="justify">O primeiro problema mapeado foi, quando eu rodei o docker compose ele me retornou um erro, conforme está sendo mostrado abaixo, veja:</p>

```sh
> Executing task: docker-compose -f "docker-compose.yaml" up -d --build <

ERROR: Service "web" uses an undefined network "frontend"
O processo de terminal "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -Command docker-compose -f "docker-compose.yaml" up -d --build" foi terminado com o código de saída: 1.
```

<p align="justify">O docker compose não estava buildando o projeto e assim estava retornando o erro que foi apresentado a cima, com isso fiz mais uma verificação e mapeamento nos arquivos do compose e dockerfile para que eu pudesse análisar com mais critérios como estava configurando e assim, pude aplicar as ações para poder sanar esse problema.</p>

<p align="justify">Feitas as modificações cabíveis, executei o docker compose e desenvolvi a aplicação baseada no arquivo YAML.</p>

<p align="justify">Depois que a aplicação foi alterada e construída para poder ser executada, percebi que alguns serviços estavam em down, análisei mais uma vez o arquivo de Dockerfile e também do docker compose com o intuito de poder identiicar se as portas estavam sendo declaradas corretamente. Depois de feito isso pude observar que as portas que haviam sido declaradas estavam invertidas e que o redis não tinha uma porta definida; identifiquei isso, fiz a correção nos arquivos Dockerfile e docker compose e, o serviço writer subiu(se tornou up).</p>

###### - EXECUTANDO SERVIÇOS

<p align="justify">Novamente fiz mais uma análise na aplicação de uma maneira mais geralzona e fiz a execução dos serviços de uma maneira independentementes: web, reader, writer e o redis.</p>

###### => READER

###### => WEB

###### => REDIS
