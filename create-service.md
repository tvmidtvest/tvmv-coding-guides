## Opret service

```bash
$ sudo systemctl edit --force --full [servicenavn].service
```

Indsæt følgende i filen:

```
[Unit]
Description=[servicenavn]
Wants=network-online.target
After=network-online.target

[Service]
Type=simple
User=kalturadrop
WorkingDirectory=[absolut sti til rod-mappen af servicen]
ExecStart=[absolut sti til filen som skal eksekveres]

[Install]
WantedBy=multi-user.target
```

Check herefter at service er installeret:

```bash
$ systemctl status [servicenavn].service
```

Enable servicen og start den:

```bash
$ sudo systemctl enable [servicenavn].service
$ sudo systemctl start [servicenavn].service
```

### Brug for hjælp?

Skriv til Martin Orvad, TV MIDTVEST, maor@tvmidtvest.dk.
