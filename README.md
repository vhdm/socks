# socks
Alias to start, stop and restart socks

socks ip: 0.0.0.0

alias socksrestart="socksstop && socksstart"
alias socksstart="ssh -i ~/.ssh/id_rsa_socks -f -N -D 1080 root@0.0.0.0"
alias sockstest="curl -s -x socks5://127.0.0.1:1080 https://ifconfig.me/all.json | jq"
alias socksstop='function _socksstop(){ ps aux | grep "ssh -i /root/.ssh/id_rsa_socks -f -N -D 1080 root@0.0.0.0" | grep -v grep | awk "{print \$2}" | xargs kill -9; }; _socksstop'
