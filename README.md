# apprtc-docker

Out-of-the-box docker images for AppRTC dev/test purpose.

## AppRTC-Server

``` bash
docker run --rm \
  -p 8080:8080 -p 8089:8089 -p 3478:3478 -p 3033:3033 \
  --expose=59000-65000 \
  -e PUBLIC_IP=<server public IP> \
  -v <path to constants.py>:/apprtc_configs \
  -t -i piasy/apprtc-server
```

About port expose:

+ `8080` is used for room server;
+ `8089` is used for signal server;
+ `3033` is used for ICE server;
+ `3478` and `59000-65000` is used for TURN/STUN server;

So make sure your firewall has opened those ports.

About how to modify `constants.py`, see [this example](constants.py), `ICE_SERVER_BASE_URL`, `ICE_SERVER_URL_TEMPLATE` and `WSS_INSTANCES` has been modified.

## AppRTC-Android

todo

## AppRTC-iOS

todo
