# Setup own .onion site

## Step 1:

Create and Navigate your desire folder

- Use this command

    `mkdir <folder_name>`

    `cd <folder_name>`

Start the server on that directory

`python3 -m http.server --bind 127.0.0.1 8080`

1. Here we are using port :80 as [localhost](http://localhost) 
2. Your PC should install python
3. For checking visit your tor browser and check wheater its running

Create a HTML page on that directory

`touch index.html`

> Inside HTML file you can write any basic HTML code

## Step 2:

 Open another terminal and search for tor there

- Use this command

    `whereis tor`

It will show something like:
`tor: /usr/bin/tor /usr/sbin/tor /etc/tor /usr/share/tor /usr/share/man/man1/tor.1.gz`

Navigate to tor directory which is inside etc

- Use this command

    `cd /etc/tor`

    > use `ls` for show files inside the directory

    Write the actual port in this torrc file

    - Use this command

        `sudo nano torrc` 

        Uncomment this line: 

        `HiddenServiceDir /var/lib/tor/hidden_service/
        HiddenServicePort 80 127.0.0.1:8080`

        Compile and run torrc file

        - Use this command

            `sudo tor`

## Step 3:

 Goto your root diectory on your linux

- Use this command

    `sudo su`

Naviagte to your tor hidden service directory

- Use this command

    `cd /var/lib/tor/hidden_service/`

    > use `ls` for show files inside the directory

View your private hostname

- Use this command

    `cat hostname`

### And you can see your .onion site. Congratulations your First Dark web is running 🎉