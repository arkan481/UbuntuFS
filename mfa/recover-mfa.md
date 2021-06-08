# Recover MFA
Instructions to recover MFA when You have no longer have the phone, or the scratch code.

## Instructions
> If you have your scratch codes available, just use one of them and run the google-authenticator command again, and  You can skip these instructions, for furthermore information regarding this command please see [setting up ubuntu server](../setting-up.md), however if You need to recover the old codes please see the [Recovering old codes section](#recoveringoldcodes).

1. You have to login to your terminal somehow, in Digital Ocean you can access the console by clicking access console, and login with your user.
2. Run the google authenticator command, and set it up using your new phone, see [setting up ubuntu server](../setting-up.md).

## <a name="recoveringoldcodes"></a> Recovering old codes
> If you  somehow need to recover or use the old authenticator code, use these following steps.
1. You have to login to your terminal somehow, in Digital Ocean you can access the console by clicking access console, and login with your user.
2. Then run these following bash scripts.
```zsh
# Change working dir into user home directory
cd
# Shows google_authenticator files that contains the code
cat .google_authenticator
```