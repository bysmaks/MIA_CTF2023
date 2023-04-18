# Defender (PWN)
### Сложность
Hard
### Описание
У нас есть исполняемый файл приложения для авторизации пользователей. Можешь проверить его на наличие уязвимостей?

nc <SERVER_IP_ADDR>:17171
### Запуск
```sh
docker build -t defender .
docker run -i -dp 17171:17171 defender
```
### Флаг
CTF{3z_d3f3nd3r_w4s_pwn3d}
