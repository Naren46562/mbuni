# mbuni
MMSC open source application, where we can send MMS , ringtones, logos etc....

The Multimedia Messaging Service (MMS), is intended to provide a rich set of content to subscribers (pictures, audio, games, etc). It supports both sending and receiving of rich content by properly enabled client devices. MMS is a non-real-time delivery service, much like SMS or email. The service utilises a store-and-forward usage model.

MMS is designed to be transported largely over IP rather than traditional GSM (SS7) networks. It is also designed to interoperate with other IP services such as email and WAP. In fact, MMS messages are typically transported over WAP, and are encoded using WAP MIME formats.

Multimedia messages can be originated by or terminate to end-user client devices (i.e. MMS-enabled phones) or third party applications (typically used by MMS content providers). In the MMS architecture, the MMSC acts as the message-switching system within the core network, while the MMSBox acts as the message dispatch and content management system on the VAS (third party) side. The overall architecture is shown below.

Requirements
Mbuni is being developed on MacOS X and Linux systems using the C programming language. It should compile and run on any similar system.

Mbuni utilises some libraries that are part of the Kannel source, specifically GWLIB and WAP libraries. In order to install Mbuni you will need to install Kannel (and therefore fulfil those dependencies Mbuni shares with it).

The following additional components are required:
Libiconv v2.0 or higher is required for character set conversions
Audio conversion tools required by the content adaptation module:
Sox from sox.sourceforge.net
Lame (v3.93 or higher) from www.mp3dev.org
Mpg123 from www.mpg123.de
AMR encoder/decoder from www.3gpp.org (modified, see below)
Image conversion tools required by the content adaptation module:
o ImageMagick from www.imagemagick.org
Mail server such as Postfix (www.postfix.org)
You will also need to be running a WAP gateway (we recommend Kannel).
You may optionally need to run an HTTP proxy such as Squid (squid-cache.org), since some newer phones (e.g. Nokia 6600) do not send MMS over WAP but directly over HTTP via an HTTP Proxy.
Hardware requirements will depend on amount of traffic, required response times, etc. Keep in mind however that the gateway performs a lot of heavy multimedia re-coding tasks, particularly during content adaptation, so you should always err on the side of more rather than less power.

Installing The Gateway
This section explains the steps required to install the gateway. If you are installing from a binary distribution, you may safely skip to here.

In brief, to install Mbuni, you need to:

Download and install required packages (such as libXML, libiconv)
Download and install Kannel (v1.4.2 and above)
Download and install Mbuni
Download, patch and install the AMR encoder/decoder
Download and install additional requried packages
