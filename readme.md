
## 開發

* 啟動，於 docker 目錄下，執行指令 `docker-compose up`
* 進入 php Server，終端機執行指令 `docker exec -it oa-php73 zsh`
  * 重啟 `service apache2 restart`
* 挺止所有 container 並且移除所有 images  `docker-compose down --rmi all`

## 設定
  * 於 php server 內的 mysql host 為 `mysql`，redis 的 port 為 `redis`
  * vhost 的設定於 `php73/config/000-default.conf` 設定，設定完後進入 php server 內重啟 apache
    * 進入 `docker exec -it oa-php73 zsh`
    * 重啟 `service apache2 restart`
    * 退出 `exit`