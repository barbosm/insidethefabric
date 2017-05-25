# First day at work!

Congratulations, you just arrived at your new networking security job! Today we start a very interesting journey and just as every good story we start very small. In this chapter we'll go over some initial steps that you should do once you've just unboxed your shiny new FortiGate and need to put the network up as soon as possible.

Keep in mind that we go over some config steps without doing all considerations \(as is usually the case on real world scenarios\) and due to that sometimes we may not configure some things in the best or optimal way in the first time, but do not worry because as our knowledge increases over the book we should also fix those issues until the end of our journey.

## Turn it on

Ok, in your desk you have this small, beautiful little white box and just after turning it on you can see some leds blinking which gives you the impression that everything is working, then you connect a network cable and access the device both by HTTPS and SSH \(usually in the IP 192.168.1.99\), then login using the **user** _**admin**_ and _**nothing \(as in blank, nada\)**_ as the **password**. You're in.

```
FGT60D4613056666 #
```

Now you start configuring some basic management stuff that you'll need to no matter the initial network configuration that your boss asked to, here's what you remember from the top of your head:

* Change admin password \(Top priority!\)
* Hostname
* Admin session timeout
* Update firmware
* Check licensing and security updates

After planning the initial steps, you get to work right away.

### Change admin password

```
config system admin
    edit "admin"
        set password verygoodandsecurepassword
    next
end
```

### Hostname

### Admin session timeout

### Update firmware

### Check licensing and security updates

After you receive the network diagram you're ready to start configuring the specific settings needed to have the network up and running, here's what you plan to configure:

* Network interfaces \(physical interfaces and VLANs\)
* Static routing
* Source NAT


> #### primary::Title
> #### success::Title
> #### danger::Title
> #### warning::Title
> #### info::Title

> #### Title
>
> Content

