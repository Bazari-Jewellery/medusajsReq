## Ensure docker containers are reboot


- create a file
```sh
sudo nano /etc/systemd/system/medusa-docker-app.service
```
- paste the content of the medusa-docker-app.service file

- change the path to the docker compose file

- Check location of docker and use it for the ExecStart and ExecStop line in the file
```sh
which docker
```

- Reload systemd to recognize the new service
```sh
sudo systemctl daemon-reload
```

- Enable the service so that it starts on boot
```sh
sudo systemctl enable medusa-docker-app
```

- Start the service immediately (optional)
```sh
sudo systemctl start medusa-docker-app
```
- Note: if it seems as though the terminal is hanged. Do not fret, it is most probably pulling the docker images. You can press ctrl+c and use the ff command to check
the status of service
```sh
sudo systemctl status medusa-docker-app
```