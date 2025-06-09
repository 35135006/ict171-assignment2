# Setting Up DNS


## Creating the hostname

- go to google and open https://my.namecheap.com/
- type in the desired domain name
- pay for name

## assigning DNS
- in the EC2 SSh on ternimal enter curl ifconfig.me
- copy the ip address thats shows
- go bach to https://my.namecheap.com/
- log in
- on the side bar, click Domain list
- delete any recordds available and create a new noe
- type -> A record, Host -> A, Value -> enter Ip address copied, TTL -> automatic.
  
