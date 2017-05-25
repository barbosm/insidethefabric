# Basic Management Configuration

First let's do some generic but very important management configuration.

> info::CLI Structure
>
> You'll most likely notice that the FortiOS \(the operating system that runs on FortiGates\) is a little different from let's say [VyOS](https://vyos.io/) or a Cisco Switch where you can configure things in one line, instead in FOS you need to enter or 'get in' the relevant config section, so the config will be nested inside that specific section. A good way to explore the options inside that section is to simply type '**tree**' which will give you all options inside that section.

## Change admin password

```
config system admin
    edit "admin"
        set password verygoodandsecurepassword
    next
end
```

## Hostname

```
    set hostname "FG"
end
```

## Admin session timeout

```
    set admintimeout 60
end
```

## Update firmware

## Check licensing and security updates

## You got mail!

You're proud of all the hard work done but there is still more to come, you just received a new email from your boss, this one contains the network diagram and ip addressing for your network.

