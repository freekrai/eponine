![Eponine](https://cloud.githubusercontent.com/assets/2723/13193697/d0f48a56-d731-11e5-854a-d4743254a446.jpg)

# Eponine

Eponine is a [very tiny][server] web server in Go that accepts requests and responds with the output of shell scripts.

This was originally designed to be run on a Raspberry Pi and accessed via Slack, which is why there's a very Pi bent to the scripts. You can run it in other circumstances, though, if that's what you're into.

Starter scripts include a "who's here?" (a simple scan of MAC addresses on the local network and maps it against a known list of people in the room), and remote photo capture with the Pi's camera module.

## Install

Drop the latest binary to a directory on your machine and start the server with `./eponine`.

## Usage

Eponine can be accessed on port `24601` (haha).

The path of requests coming in get translated into shell script execution. So, a request coming in on `localhost:24601/people` will execute `./bin/people` on your machine. Needless to say, be careful of what you put in there.

Eponine will return whatever output the script outputs. If you want special formatting for Slack, for example, do it in the script.

## Scripts

Eponine will run anything in your local `bin` directory. Clone `holman/eponine-scripts` if you want the whole batch, otherwise just add them one-by-one and you'll be good.

[server]:  https://github.com/holman/eponine/blob/master/server.go
[release]: https://github.com/holman/eponine/releases
