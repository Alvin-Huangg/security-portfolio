Day 03: Listening ports on my Mac

Source: sudo lsof -iTCP -sTCP:LISTEN -n -P

Process    What it is    Needs to listen?    Why
postgres    PostgreSQL database server    Only while I'm working on a project that uses it    A database listens so my apps can connect and run queries. That is its whole job, but only when something is using it. Should be bound to 127.0.0.1 only.
mongod    MongoDB database server    Only while I'm working on a project that uses it    Same reason as Postgres. Should be bound to 127.0.0.1 only. MongoDB open to a network with no password is a classic cause of data leaks.
rapportd    Apple background service for Handoff, Universal Clipboard, and other device continuity features    Yes, if I use those features    My other Apple devices connect in to it over the local network, so it has to listen on the network, not just localhost. Managed by macOS.
ControlCe (Control Center)    AirPlay Receiver, ports 5000 and 7000    Only if I AirPlay to this Mac    It waits for an iPhone or iPad to send audio or video to the Mac. If I never do that, it can be turned off.
Adobe\x20    An Adobe Creative Cloud background helper. \x20 is an escaped space, and lsof cuts names to 9 characters    Yes, while I use Adobe apps    Adobe apps and the Creative Cloud helper talk to each other through a local port (sign-in, licensing, sync). Should be 127.0.0.1 only.
Discord    Discord desktop app    Not for chatting, optional otherwise    Messages and voice use outbound connections. The listening port is a local helper so my browser and games can talk to the app (opening invite links, showing what I'm playing). Should be 127.0.0.1 only.
OneDrive    Microsoft's cloud file sync (not Outlook)    Only if I use OneDrive sync    Syncing itself is outbound. The local port lets Finder and Office apps talk to the sync client. Should be 127.0.0.1 only.
figma_age (figma_agent)    Figma's font helper    Only if I use fonts installed on my Mac in Figma    Figma connects to it locally to read my installed fonts. It keeps running even when Figma is closed. Should be 127.0.0.1 only.
Spotify    Spotify desktop app    Not for playing music, optional otherwise    Streaming is outbound. It listens so other devices on my network can find and control it (Spotify Connect). Only open while the app is running.
