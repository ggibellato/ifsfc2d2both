Este projeto usa git submodules (https://git-scm.com/docs/gitsubmodules)

apos voe clonar o projeto mude para o diretorio ifsfc2d2both e execute:

git submodule update --init --recursive

isto ira trazer o codigo dos outros 2 projetos

Para executar os o servidor e o cliente usando kubernetes e preciso executar:

{noformat}
kubectl port-forward service/d2svr-service 3000:3000 
e
kubectl port-forward service/d2cli-service 3001:3000 
{noformat}
lembrando estou usando kind como sugerido no desafio.

Como informacao este sao os pods que tenho no meu kubernetes
{noformat}
NAME                        READY   STATUS    RESTARTS   AGE
d2cli-7b595dc769-b9jkf      1/1     Running   1          2d5h
d2svr-566547db6f-zjhcg      1/1     Running   1          2d6h
frontend-6648678fd5-5xrmq   1/1     Running   1          2d5h
{noformat}
e estes sao os servicoes
{noformat}
NAME            TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
d2cli-service   LoadBalancer   10.107.13.18     <pending>     3000:30871/TCP   2d5h
d2svr-service   LoadBalancer   10.107.138.205   <pending>     3000:30065/TCP   2d6h
kubernetes      ClusterIP      10.96.0.1        <none>        443/TCP          2d10h
{noformat}
Todos criados usando

kubectl apply -f .... (respectivo arquivo)


