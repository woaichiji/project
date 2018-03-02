### https://blog.phpgao.com/carzy_router.html

自动更新
# 每天凌晨4点更新文件，注意文件路径
## 拿到中国ip
0 4 * * * curl 'http://ftp.apnic.net/apnic/stats/apnic/delegated-apnic-latest' | grep ipv4 | grep CN | awk -F\| '{ printf("%s/%d\n", $4, 32-log($5)/log(2)) }' > /etc/chinadns_chnroute.txt
