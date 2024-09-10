# Домашнее задание к занятию «Kubernetes. Причины появления. Команда kubectl»

## Задание 1. Установка MicroK8S
microk8s установлен
![image](https://github.com/user-attachments/assets/e9bce03a-c3e7-4434-92ad-ec159c6f81ec)

Устанавливаем и включаем дашборд
![image](https://github.com/user-attachments/assets/5548787a-9ef8-400c-bf97-80a3536765b5)

Генерируем токен командой `microk8s kubectl describe secret -n kube-system microk8s-dashboard-token`
Редактируем файл /var/snap/microk8s/current/certs/csr.conf.template и обновляем конфигурацию
`microk8s refresh-certs --cert front-proxy-client.crt`

Пробрасываем порт, я взял 10443 `microk8s kubectl port-forward -n kube-system service/kubernetes-dashboard --address 0.0.0.0 10443:443` и авторизовываемся под токеном, полученным ранее
![image](https://github.com/user-attachments/assets/de75e7ad-1b16-41b5-90c1-181bfd4fef0b)
![image](https://github.com/user-attachments/assets/fe068192-77dd-47bf-af56-c565a48d6692)

## Задание 2. Установка и настройка локального kubectl

После установки дублируем конфиг minik8s в kubectl

![image](https://github.com/user-attachments/assets/9dfc84d9-d509-47e4-aece-296b34da62d6)

В дашборде видим те же поды, что и увидели через kubectl

![image](https://github.com/user-attachments/assets/838c8242-8f5a-4378-8827-34a1bd89044b)
