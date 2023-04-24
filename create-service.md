# Opret en service på en Debian

Instruktioner på hvordan man opretter en service på en Debian, hvis scriptet skal holde øje med et eller andet, og derfor ikke kan køre som et cronjob. Cronjobs er i øvrigt _næsten_ altid at foretrække, da det er meget lettere at håndtere.

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
ExecStart=[absolutte stier til python i .venv og til filen som skal eksekveres]

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
