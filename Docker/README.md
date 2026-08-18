### A Sample Configuration
{ 
	"registry-mirrors": ["https://*URL","https://*URL*"] ,

    # Docker IP Pools Configuration
	"default-address-pools": [
		{
			"base":"192.168.1.0/24",
			"size":24
		},
		{
			"base": "172.16.0.0/16",
			"size": 24
		},
		{
			"base": "10.0.0.0/16",
			"size": 24
		}
	],
    
	"log-driver": "loki",
    	"log-opts": {
        	"loki-url": "https://User:Pass@loki.local/loki/api/v1/push"
    }
}
