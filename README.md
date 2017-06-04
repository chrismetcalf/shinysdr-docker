Docker container config for the [ShinySDR](https://github.com/kpreid/shinysdr) web-based software defined radio client.

You'll probably want to create your own version of `config.py` and map your own `/config` directory. Depending on the source of your SDR data, you may be able to get away with a TCP connection, but I needed to run in "privileged" mode to give my container access to the RTL device. My `docker run` command:

```
docker run --name shinysdr -p 8100:8100 -p 8101:8101 -v /directory/where/i/put/docker/shinysdr:/config --privileged chrismetcalf/shinysdr-docke
```

Then connect to port 8100 on your container, and have fun!
