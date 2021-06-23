# skillfactorytask13

ссылка на гитлаб https://gitlab.com/victordutovski/podinfo/activity

13.3 

Адаптируйте Makefile для использования в GitLab и используйте команды make в .gitlab-ci.yml

Для корректной работы на машине, которая используется в качестве gitlab-runner нужны:

docker, git, make, gitlab-runner.

Использовал обычный ранер с shell

13.4

Подключите Kubernetes из Яндекс.Облака. Разверните приложение в Kubernetes с помощью helm.

Собрал скриншоты и логи.

Подключил Kubernetes к gitlab(использовал https://docs.gitlab.com/ee/user/project/clusters/add_existing_cluster.html, https://cloud.yandex.ru/docs/solutions/infrastructure-management/gitlab-containers).

Настроил ранеры на запуск в kubernetes(Использовал это https://docs.gitlab.com/runner/install/kubernetes.html и это https://habr.com/ru/post/481662/)

***********************************************************
Может не работать helm update ( Error: UPGRADE FAILED: query: failed to query with labels: secrets is forbidden: User "system:serviceaccount:gitlab:default" cannot list resource "secrets" in API group "" in the namespace "gitlab"), 

нужно использовать это:

kubectl create clusterrolebinding gitlab-cluster-admin --clusterrole=cluster-admin --group=system:serviceaccounts
************************************************************

Не понял как настроить подключение к развернутому сервису.

Пытался сделать по https://cloud.yandex.ru/docs/managed-kubernetes/operations/create-load-balancer#simple-app но пока не получилось.
