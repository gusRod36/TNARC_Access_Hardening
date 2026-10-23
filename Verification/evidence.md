## F1: Telnet vs SSH

#### Before

<img src="./before/f1-telnet-vs-ssh.JPG" alt="version before" width="650">
<img src="./before/f1-telnet-vs-ssh-version.JPG" alt="version before" width="650">
<img src="./before/f1-telnet-vs-ssh-sshlogin.JPG" alt="ssh before" width="650">

#### After

<img src="./after/f1-telnet-vs-ssh.JPG" alt="version" width="650">

## F2: AAA login, plus local fall back

<img src="./after/aaa-down-locallogin.JPG" alt="aaa" width="650">

## F3: Rogue DHCP

#### Before

<img src="./before/f3-rogue-dhcp-broken-defaultgw.JPG" alt="RD before" width="650">

Here we can see the PC was being handed a broken default gateway by the Rogue DHCP server

#### After

<img src="./after/f3-rogue-dhcp.JPG" alt="after" width="650">

No matter how many attempts were tried the correct server always handed out the DHCP messages.

## F4: ARP-Inspection

#### Before

<img src="./before/f4-no-dai.JPG" alt="before" width="650">

#### After 

<img src="./after/f4-DAI.JPG" alt="after">

## F5: Port-Security

#### Before

<img src="./before/f6-RogueSwitch.JPG">

#### After

<img src="./after/port-security-unauthorized-device.JPG">

<img src="./after/psecure-and-stickymac.JPG" alt="" width="650">

here we have a rogue switch and an Unknown device being blocked by psecure.

## F6: Rogue Switch

<img src="./after/port-security-rogue-switch.JPG" alt="" width="650">
<img src="./after/psecure-err-disabled.JPG" alt="" width="650">

## F7: Management Access Restricted

<img src="./after/f7-ACLs.JPG" alt="" width="650">

## F8: Password Encryption

#### Before

<img src="./before/f2-unencrypted-vs-encrypted.JPG" alt="" width="650">

#### After

<img src="./after/f8-password-encrypted.JPG" alt="" width="650">

## F9: Session limits

<img src="./after/f9-exec-timeout.JPG" alt="" width="650">

## F10: Banner

<img src="./after/banner.JPG" alt="" width="650">