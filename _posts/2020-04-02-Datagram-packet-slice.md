---
excerpt: Datagram packet slice framework
category: network
keyword: datagram,socket,packet,slice,split
---

### About

Auto slice and merge datagram packet, no need care about packet size.

---

### Download

Add maven repository url `https://dl.bintray.com/pacey6/maven`.

Download the latest JAR at the coordinates `com.pacey6.net:datagram:1.0`.

---

### Source Code

See [Github](https://github.com/Pacey6/Datagram).

---

### Usage

* Create MultiDatagramSocket:

```java
MulticastSocket multicastSocket = new MulticastSocket(1027);
MultiDatagramSocket<MulticastSocket> multiDatagramSocket = new MultiDatagramSocket<>(multicastSocket);
```

* Receive packet, method `receive()` will block current thread:

```java
MultiDatagramPacket multiDatagramPacket = multiDatagramSocket.receive();
String msg = new String(multiDatagramPacket.getData());
```

* Send a packet:

```java
String msg = "Hello world";
MultiDatagramPacket multiDatagramPacket = new MultiDatagramPacket(msg.getBytes(), InetAddress.getLocalHost(), 1027);
multiDatagramSocket.send(multiDatagramPacket);
```

