## RFC: teamfn overall design

This is a living document.

## Overall System Description

`teamfn` is a real-time event and notification system for team- and project-based work/status tracking. The system is comprised of a cluster of servers that manage connections with multiple clients running in browsers or mobile applications.

### Server Design

The core `teamfn` server is a websocket-based server for real-time communications. Events, messages, notifications, etc. will be sent over websockets between clients and servers.

The server uses a pub-sub system for events. This will be described in more detail in a further section.

### Prototype Server Design?

Technologically speaking, a `socket.io`-compatible server looks to be the most reasonable choice, rather than defaulting to raw websockets, and because we probably won't be implementing this server in something like Clojure (at least, not yet).

### Client Design

TBD

### Add-on/hook system

Much of the work in the system is performed by hooks and plugins that interface with systems beyond the core server. For example, a team working on a software project hosted on Github might want a hook that interfaces with Github for things like commit tracking and issue statuses.

## Software Design
