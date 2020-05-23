# Turn on the Google BBR on CentOS8
there is an easy way if you have kernel version above 4.9.0
type this to display the current version:
`uname -R`

## Just three steps to turn on BBR
Line by line to input:

`echo 'net.core.default_qdisc=fq' | sudo tee -a /etc/sysctl.conf`

`echo 'net.ipv4.tcp_congestion_control=bbr' | sudo tee -a /etc/sysctl.conf`

`sudo sysctl -p`

and then, to check if BBR works:

`sudo sysctl net.ipv4.tcp_available_congestion_control` 

get answer will be:
`net.ipv4.tcp_available_congestion_control = bbr cubic reno`

Next, input:

`sudo sysctl -n net.ipv4.tcp_congestion_control`

get answer:
`bbr`

Finally:

`lsmod | grep bbr`

get an answer like:
`tcp_bbr                20480  1`
