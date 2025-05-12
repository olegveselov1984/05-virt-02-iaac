  GNU nano 4.8                                                        /src/mydebian.json                                                                  
{
    "builders": [
        {
            "type": "yandex",
            "token": "XXXXX,
            "folder_id": "b1gtnnmljkg2pphuqpge",
            "zone": "ru-central1-d",
            "image_name": "debian-11-docker",
            "image_description": "my custom debian with docker",
            "source_image_family": "debian-11",
            "subnet_id": "fl8pqkoh8ade6kqram0k",
            "use_ipv4_nat": true,
            "disk_type": "network-hdd",
            "ssh_username": "debian"
        }
    ],
    "provisioners": [
    {
      "type": "shell",
      "inline": [
        "#!/bin/bash",
"sudo apt-get update",
"sudo DEBIAN_FRONTEND='noninteractive' apt-get install -y ca-certificates curl htop tmux",
"curl -fsSL https://get.docker.com -o get-docker.sh",
"sudo sh get-docker.sh"
           ]
    }
    ]
}
