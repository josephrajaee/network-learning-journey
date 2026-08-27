# Networking Learning Journey — Roadmap V2

> **Target:** 30–40 days  
> **Default study time:** 60–90 minutes per day  
> **Primary goal:** Deep networking understanding for a software/backend engineer  
> **Secondary goal:** Broad coverage of CompTIA Network+ N10-009  
> **Method:** Mission-based, lab-driven, visual, troubleshooting-first, AI-assisted

---

# 1. What This Roadmap Optimizes For

This is not a certification-cram plan.

The goal is to become able to reason about questions such as:

```text
What happens when HttpClient sends a request?
Why does my machine need a default gateway?
Why is the destination MAC different from the destination IP?
Why can DNS work while TCP fails?
Why can an API reach PostgreSQL locally but not remotely?
Why does latency increase under packet loss?
What does a reverse proxy actually do on the network?
How do Docker containers communicate?
How do I prove where a network failure is?
```

Network+ N10-009 is used as a **coverage boundary**, not as the teaching order.

Current official N10-009 domain weights:

```text
Networking Concepts       23%
Network Implementation    20%
Network Operations        19%
Network Security          14%
Network Troubleshooting   24%
```

Because the goal is real understanding, this roadmap gives extra practical weight to:

```text
Fundamentals
Packet flow
IP addressing
Subnetting
Routing
TCP/UDP
DNS
Wireshark
Troubleshooting
Backend/network integration
```

---

# 2. Duration Model

The roadmap contains:

```text
34 core Missions
4 Checkpoint / Repair sessions
```

Expected completion:

```text
Fast pace:       ~30–32 days
Normal pace:     ~34–38 days
With weak-topic repair: up to 40 days
```

A Mission is not forced to equal one calendar day.

Some Missions may take:

```text
40 minutes
```

while important Missions such as:

```text
Subnetting
Routing
TCP
DNS
Wireshark
```

may require more than one normal session.

---

# 3. Daily Modes

## Standard Mode

```text
60–90 minutes

5–10 min   Spaced recall
20–30 min  New concept
10–15 min  Reasoning / explain-back
15–25 min  Lab / packet observation
5–10 min   Review + progress update
```

## Minimum Mode

Use when time or energy is low:

```text
20 minutes

5 min   Recall
10 min  One small concept or challenge
5 min   Explain-back
```

Minimum Mode preserves continuity.

Do not start a large new Mission in Minimum Mode.

## Light Review Mode

Approximately every 6–7 study sessions:

```text
30–60 minutes

spaced recall
mixed scenario
weak-topic repair
one old packet capture
no large new topic
```

---

# 4. Mastery Scale

Each important concept is tracked using:

```text
0 — Unknown
1 — Recognize
2 — Understand
3 — Explain
4 — Apply
5 — Analyze / Troubleshoot
6 — Transfer to a new scenario
```

For core networking concepts, the target is usually:

```text
Level 5–6
```

For broad Network+ topics, Level 1–3 may be sufficient.

---

# 5. Roadmap Overview

```text
Phase 1  — Network Mental Model
Phase 2  — Ethernet, MAC and Local Delivery
Phase 3  — IPv4, Subnetting and Routing
Phase 4  — Transport and Application Services
Phase 5  — LANs, Infrastructure and Security
Phase 6  — Operations, Cloud and Modern Networking
Phase 7  — Developer / Linux / Container Networking
Phase 8  — Troubleshooting and Packet Analysis
Phase 9  — Integrated Capstone
```

The recurring spine of the entire roadmap is:

```text
Follow the Packet
```

We repeatedly revisit one application request and add more detail as knowledge grows.

---

# PHASE 1 — Build the Network Mental Model

## Mission 01 — What Is a Network?

**Priority:** Essential  
**Target mastery:** 3  
**Estimated time:** 45–60 min

Learn:

```text
host
network
communication
LAN
WAN
Internet
network interface
basic network path
```

Main question:

> What must exist for two computers to exchange data?

Backend connection:

```text
Client → Network → API Server
```

Lab:

```text
Get-NetAdapter
ipconfig
ping
```

Visual:

```text
Laptop → Router → Internet → Server
```

Repository artifact:

```text
missions/01-what-is-a-network/review.md
```

---

## Mission 02 — Hosts, NICs and Network Interfaces

**Priority:** Essential  
**Target mastery:** 4  
**Estimated time:** 60 min

Learn:

```text
host
NIC
interface
physical vs virtual interface
link state
IP configuration
```

Lab:

```text
Get-NetAdapter
Get-NetIPAddress
ipconfig /all
```

Predict before lab:

> Which interface is currently carrying Internet traffic?

Backend connection:

> Which interface does a backend process ultimately use to send traffic?

Visual:

```text
Application
   ↓
Operating System
   ↓
Network Interface
   ↓
Network
```

---

## Mission 03 — Data, Packets, Frames and Encapsulation

**Priority:** Essential  
**Target mastery:** 4  
**Estimated time:** 60–75 min

Learn:

```text
data
segment
packet
frame
bits
encapsulation
decapsulation
payload
header
```

Mental model:

```text
HTTP Data
   ↓
TCP Segment
   ↓
IP Packet
   ↓
Ethernet Frame
   ↓
Bits
```

Lab:

Inspect a real connection using:

```text
netstat
Get-NetTCPConnection
```

Visual:

Encapsulation stack.

---

## Mission 04 — OSI and TCP/IP Without Memorization

**Priority:** Essential  
**Target mastery:** 4  
**Estimated time:** 60–75 min

Learn:

```text
OSI model
TCP/IP model
layer responsibilities
abstraction
end-to-end vs hop-to-hop
```

Do not focus on memorizing seven layer names only.

Main exercise:

Map:

```text
HTTP
TLS
TCP
IP
Ethernet
```

to the models.

Backend connection:

Trace an ASP.NET Core request through the stack.

Visual:

OSI ↔ TCP/IP mapping.

---

# CHECKPOINT 01 — Mental Model

**Suggested calendar position:** Day 4–5

Test:

- explain packet vs frame
- explain encapsulation
- identify active interface
- map HTTP/TCP/IP/Ethernet
- trace a simple request

Create:

```text
checkpoints/checkpoint-01/
```

Do not continue if the basic packet mental model is still weak.

---

# PHASE 2 — Ethernet, MAC and Local Delivery

## Mission 05 — Ethernet

**Priority:** Essential  
**Target mastery:** 5  
**Estimated time:** 60–75 min

Learn:

```text
Ethernet
frame
source MAC
destination MAC
EtherType
MTU
broadcast
```

Lab:

Inspect Ethernet frames in Wireshark.

Visual:

Ethernet frame + local LAN.

---

## Mission 06 — MAC Addresses and Switching

**Priority:** Essential  
**Target mastery:** 5  
**Estimated time:** 60–75 min

Learn:

```text
MAC address
unicast
broadcast
switch
MAC address table
forwarding
flooding
collision domain
broadcast domain
```

Lab:

Observe MAC addresses on the local machine.

Packet Tracer:

Simple two-host + switch topology.

Visual:

Switch forwarding decision.

---

## Mission 07 — ARP and Local Delivery

**Priority:** Essential  
**Target mastery:** 6  
**Estimated time:** 75–90 min

Learn deeply:

```text
ARP request
ARP reply
ARP cache
IP → MAC resolution
local vs remote destination
gateway MAC
```

Critical mental model:

```text
Final destination IP:
remote server

Current-hop destination MAC:
next hop
```

Prediction lab:

1. inspect ARP cache
2. predict the next ARP
3. generate traffic
4. capture ARP in Wireshark
5. compare prediction with reality

Commands:

```text
arp -a
Get-NetNeighbor
ping
```

Capture:

```text
captures/arp-request-reply.pcapng
```

Visual:

Local destination vs remote destination ARP flow.

---

## Mission 08 — Switching Deeper: VLAN Preview and Broadcast Domains

**Priority:** Important  
**Target mastery:** 4  
**Estimated time:** 45–60 min

Learn:

```text
why large flat LANs are undesirable
broadcast domain
logical segmentation
basic VLAN idea
```

Do not deeply configure VLANs yet.

Purpose:

Prepare the mental model for later LAN design.

---

# PHASE 3 — IPv4, Subnetting and Routing

## Mission 09 — IPv4 Addressing

**Priority:** Essential  
**Target mastery:** 5  
**Estimated time:** 75–90 min

Learn:

```text
IPv4 address
32 bits
network portion
host portion
CIDR
subnet mask
private ranges
loopback
APIPA/link-local
```

Lab:

```text
ipconfig
Get-NetIPAddress
```

Reasoning:

Identify which part of an address represents the network.

Visual:

32-bit IPv4 address.

---

## Mission 10 — Binary and Subnetting Foundations

**Priority:** Essential  
**Target mastery:** 5  
**Estimated time:** 75–90 min

Learn only the binary needed for networking.

Learn:

```text
powers of two
binary ↔ decimal
prefix length
network address
broadcast address
usable range
```

Practice:

```text
/24
/25
/26
/27
/28
```

Do calculations yourself before using tools.

---

## Mission 11 — Subnetting Mastery

**Priority:** Essential  
**Target mastery:** 6  
**Estimated time:** 75–90+ min

Learn:

```text
subnet boundaries
host ranges
subnet count
host capacity
VLSM concept
```

Challenge:

Given arbitrary hosts, design suitable subnets.

Backend connection:

Design separate:

```text
API
Database
Management
```

subnets.

Visual:

Address-space partition.

---

## Mission 12 — Routing Decisions and Default Gateway

**Priority:** Essential  
**Target mastery:** 6  
**Estimated time:** 75–90 min

Learn deeply:

```text
routing table
destination network
next hop
default route
longest-prefix match
directly connected route
metric
```

Commands:

```text
route print
Get-NetRoute
tracert
```

Critical question:

> How does the OS decide where an IP packet goes next?

Visual:

Routing table → next-hop decision.

---

## Mission 13 — Routers, Hops, TTL and ICMP

**Priority:** Essential  
**Target mastery:** 5  
**Estimated time:** 60–75 min

Learn:

```text
router
hop
TTL
ICMP
echo request/reply
destination unreachable
time exceeded
traceroute
```

Lab:

```text
ping
tracert
```

Observe ICMP in Wireshark.

Explain:

What changes and what stays the same across routers?

---

## Mission 14 — MTU, Fragmentation and Path MTU

**Priority:** Important  
**Target mastery:** 3–4  
**Estimated time:** 45–60 min

Learn:

```text
MTU
fragmentation concept
Path MTU
why packet size matters
```

Backend connection:

Understand why some network paths behave strangely with large packets or tunnels.

---

## Mission 15 — IPv6 Essentials

**Priority:** Important / Network+  
**Target mastery:** 3–4  
**Estimated time:** 60–75 min

Learn:

```text
IPv6 format
128-bit addressing
link-local
global unicast
multicast
no broadcast
NDP concept
SLAAC
```

Do not over-invest in manual IPv6 arithmetic.

Compare:

```text
ARP ↔ NDP
IPv4 ↔ IPv6
```

---

# CHECKPOINT 02 — IP and Routing

Test:

```text
IPv4
subnetting
local vs remote
ARP
routing table
default gateway
ICMP
```

Mandatory scenario:

```text
Host A
192.168.10.50/24

Gateway
192.168.10.1

Server
10.20.30.40
```

Explain the first-hop journey completely.

Save:

```text
checkpoints/checkpoint-02/
```

---

# PHASE 4 — Transport and Network Services

## Mission 16 — Ports, Sockets and Processes

**Priority:** Essential  
**Target mastery:** 5  
**Estimated time:** 60–75 min

Learn:

```text
port
socket
client port
server port
ephemeral port
listening socket
connection tuple
```

Backend examples:

```text
Kestrel :5000
PostgreSQL :5432
HTTPS :443
```

Lab:

```text
netstat -ano
Get-NetTCPConnection
```

Connect sockets to actual processes.

---

## Mission 17 — TCP: Connection and Reliability

**Priority:** Essential  
**Target mastery:** 6  
**Estimated time:** 75–90 min

Learn deeply:

```text
SYN
SYN-ACK
ACK
sequence numbers
acknowledgements
retransmission
ordered delivery
connection states
FIN
RST
```

Wireshark:

Capture a real TCP handshake.

Save:

```text
captures/tcp-three-way-handshake.pcapng
```

Backend connection:

What happens before an HTTP request is sent?

Visual:

TCP sequence diagram.

---

## Mission 18 — TCP Performance: Windowing and Congestion

**Priority:** Essential for real systems  
**Target mastery:** 4–5  
**Estimated time:** 60–75 min

Learn conceptually:

```text
receive window
flow control
congestion
round-trip time
retransmission
bandwidth-delay effect
```

Do not dive into kernel-algorithm internals yet.

Main question:

> Why can a high-bandwidth network still feel slow?

---

## Mission 19 — UDP

**Priority:** Essential  
**Target mastery:** 4  
**Estimated time:** 45–60 min

Learn:

```text
connectionless
datagram
no delivery guarantee
no ordering guarantee
low overhead
```

Compare TCP vs UDP by problem, not by memorized table.

Examples:

```text
DNS
streaming
real-time communication
QUIC concept
```

---

## Mission 20 — DNS

**Priority:** Essential  
**Target mastery:** 6  
**Estimated time:** 75–90 min

Learn deeply:

```text
resolver
recursive resolution
authoritative server
root
TLD
A
AAAA
CNAME
MX
TXT
NS
TTL
cache
```

Lab:

```text
nslookup
Resolve-DnsName
dig
```

Wireshark:

Capture DNS query/response.

Save:

```text
captures/dns-query-response.pcapng
```

Troubleshooting:

```text
ping 8.8.8.8 works
google.com fails
```

Backend connection:

DNS behavior of API/database clients.

Visual:

DNS resolution hierarchy.

---

## Mission 21 — DHCP

**Priority:** Essential  
**Target mastery:** 4–5  
**Estimated time:** 60–75 min

Learn:

```text
DORA
lease
scope
reservation
gateway option
DNS option
```

Observe current lease information.

Visual:

Discover → Offer → Request → Acknowledge.

Troubleshooting:

Incorrect address / missing gateway / APIPA.

---

## Mission 22 — NAT and PAT

**Priority:** Essential  
**Target mastery:** 5  
**Estimated time:** 60–75 min

Learn:

```text
private address
public address
NAT
PAT
translation table
source translation
port mapping
```

Critical question:

> How can many private hosts share one public IP?

Backend connection:

Understand inbound publishing vs outbound NAT.

Visual:

Private clients → one public IP.

---

## Mission 23 — HTTP, HTTPS and TLS on the Network

**Priority:** Essential for backend developers  
**Target mastery:** 5  
**Estimated time:** 75–90 min

Learn at networking depth:

```text
HTTP request/response
HTTP versions overview
HTTPS
TLS handshake concept
certificate
SNI concept
connection reuse
HTTP/2 multiplexing concept
HTTP/3 / QUIC overview
```

Do not turn this Mission into a cryptography course.

Lab:

```text
curl -v
browser DevTools
Wireshark
```

Follow:

```text
DNS → TCP → TLS → HTTP
```

---

# CHECKPOINT 03 — End-to-End Web Request

Explain:

```text
HttpClient
   ↓
DNS
   ↓
Route
   ↓
ARP
   ↓
Ethernet
   ↓
Router/NAT
   ↓
TCP
   ↓
TLS
   ↓
HTTP
```

Use a real website or test endpoint.

Save a short written explanation in:

```text
checkpoints/checkpoint-03/
```

---

# PHASE 5 — LAN Infrastructure and Security

## Mission 24 — VLANs and Trunks

**Priority:** Essential / Important  
**Target mastery:** 5  
**Estimated time:** 75–90 min

Learn:

```text
VLAN
access port
trunk
802.1Q
broadcast-domain separation
inter-VLAN routing concept
native VLAN concept
```

Packet Tracer lab:

Create two VLANs.

Verify isolation.

Visual:

One switch, multiple logical networks.

---

## Mission 25 — Switching Reliability: STP and Loop Prevention

**Priority:** Important / Network+  
**Target mastery:** 3–4  
**Estimated time:** 45–60 min

Learn:

```text
Layer-2 loop
broadcast storm
STP purpose
root bridge concept
blocked path
```

Focus on the problem STP solves.

Do not dive into CCNP-level STP tuning.

---

## Mission 26 — Routing Technologies

**Priority:** Important / Network+  
**Target mastery:** 3–4  
**Estimated time:** 60–75 min

Learn:

```text
static route
dynamic routing
distance vector concept
link state concept
OSPF
BGP high-level role
route selection
administrative concepts at Network+ depth
```

Do not turn this into a full CCNA routing course.

Packet Tracer:

small routed topology.

---

## Mission 27 — Firewalls, ACLs and Network Segmentation

**Priority:** Essential  
**Target mastery:** 5  
**Estimated time:** 60–75 min

Learn:

```text
firewall
stateful filtering
ACL
allow/deny
inbound/outbound
zones
segmentation
least privilege
```

Backend scenario:

```text
Internet → API :443 allowed
Internet → PostgreSQL :5432 denied
API → PostgreSQL :5432 allowed
```

Troubleshooting:

DNS works but port is blocked.

Visual:

Trust boundaries.

---

## Mission 28 — VPN, Proxy, Reverse Proxy, Load Balancer and CDN

**Priority:** Essential for backend/system design  
**Target mastery:** 4–5  
**Estimated time:** 75–90 min

Compare by problem:

```text
VPN
forward proxy
reverse proxy
load balancer
CDN
```

Backend examples:

```text
Nginx
YARP
Cloudflare
application gateway
```

Critical question:

> Where does the TCP/TLS connection actually terminate?

Visual:

Client → edge → proxy/load balancer → backend.

---

## Mission 29 — Wireless Networking

**Priority:** Important / Network+  
**Target mastery:** 3  
**Estimated time:** 60–75 min

Learn:

```text
SSID
BSSID
2.4 GHz
5 GHz
6 GHz
channels
interference
WPA2/WPA3
access point
controller
roaming concept
```

Focus on real troubleshooting and Network+ breadth.

---

# PHASE 6 — Operations, Physical and Modern Networking

## Mission 30 — Monitoring and Network Operations

**Priority:** Important  
**Target mastery:** 3–4  
**Estimated time:** 60–75 min

Learn:

```text
SNMP
Syslog
flow data
interface counters
baseline
latency
packet loss
jitter
availability
configuration backup
change management
```

Connect to observability concepts used in backend systems.

---

## Mission 31 — Physical Networking and Network+ Breadth

**Priority:** Network+ breadth  
**Target mastery:** 1–3  
**Estimated time:** 60–75 min

Learn enough to recognize and reason about:

```text
copper
fiber
single-mode
multimode
transceivers
PoE
common connectors
patch panel
MDF/IDF
cable faults
```

Do not waste large study time memorizing obscure historical details.

---

## Mission 32 — Cloud, Virtualization and Modern Network Concepts

**Priority:** Important  
**Target mastery:** 2–4  
**Estimated time:** 75–90 min

Learn:

```text
virtual switch
virtual NIC
VPC/VNet concept
public/private subnet
security group concept
cloud route table
SDN
SD-WAN
VXLAN concept
Zero Trust
SASE/SSE overview
Infrastructure as Code concept
```

Goal:

Recognize modern network architecture and understand why abstraction exists.

Do not attempt vendor-specific cloud certification depth.

---

# CHECKPOINT 04 — Infrastructure and Operations

Mixed test:

```text
VLAN
routing
firewall
proxy
load balancer
wireless
monitoring
cloud
```

One design exercise:

> Design basic network boundaries for a web API and database.

One troubleshooting exercise.

---

# PHASE 7 — Networking for Software Engineers

## Mission 33 — Linux Networking

**Priority:** Essential for developers  
**Target mastery:** 4–5  
**Estimated time:** 75–90 min

Learn commands:

```text
ip addr
ip link
ip route
ip neigh
ss
ping
traceroute
dig
curl
tcpdump
nc
```

Map Windows concepts to Linux concepts.

Goal:

Be comfortable diagnosing networking from a Linux server.

---

## Mission 34 — Docker and Container Networking

**Priority:** Essential for backend developers  
**Target mastery:** 4–5  
**Estimated time:** 75–90 min

Learn:

```text
network namespace concept
container interface
bridge network
host networking concept
port publishing
DNS between containers
container → host
container → Internet
```

Lab:

Use a small Docker Compose stack.

Example:

```text
API
  ↓
PostgreSQL
```

Observe:

```text
container IP
DNS name
published port
network path
```

---

# PHASE 8 — Troubleshooting and Packet Analysis Intensive

These sessions may be used inside the 30–40 day window depending on progress.

## Integrated Session A — Wireshark Intensive

**Target mastery:** 5

Practice filters and packet interpretation for:

```text
ARP
ICMP
DNS
TCP
TLS
HTTP
```

Goal:

Answer:

> What happened on the wire?

not merely:

> Which filter should I type?

---

## Integrated Session B — Performance Troubleshooting

Learn to distinguish:

```text
bandwidth
throughput
latency
RTT
jitter
packet loss
retransmissions
DNS delay
TCP connection delay
server delay
```

Scenario:

> API requests are “slow”.

Build an evidence-driven investigation.

---

## Integrated Session C — Broken Network Challenge

Unknown failure.

Possible causes:

```text
wrong IP
wrong mask
wrong gateway
DNS failure
route failure
firewall
closed port
VLAN mismatch
service not listening
packet loss
```

Do not reveal the failure in advance.

Use evidence.

---

## Integrated Session D — Final Follow-the-Packet

Explain completely:

```text
.NET HttpClient
       ↓
DNS
       ↓
OS routing decision
       ↓
ARP/NDP
       ↓
Ethernet/Wi-Fi
       ↓
switch
       ↓
router
       ↓
NAT
       ↓
Internet
       ↓
remote network
       ↓
TCP
       ↓
TLS
       ↓
reverse proxy/load balancer
       ↓
Kestrel
       ↓
ASP.NET Core
       ↓
PostgreSQL
```

Explain which pieces are:

```text
end-to-end
hop-to-hop
local
remote
stateful
cached
```

This is one of the primary graduation tests.

---

# PHASE 9 — Capstone

## Capstone Part 1 — Build the Network

Create a small lab representing a realistic application environment.

Example:

```text
                    Internet
                       │
                    Router
                       │
                 ┌─────┴─────┐
                 │           │
              VLAN 10     VLAN 20
              App Tier    Data Tier
                 │           │
             API Server   PostgreSQL
```

Add when practical:

```text
DNS
DHCP
NAT
routing
VLAN
firewall rules
client
API
database
```

Tools may include:

```text
Packet Tracer
Docker
Linux/WSL
local machine
```

Document the topology.

---

## Capstone Part 2 — Break and Troubleshoot

Introduce multiple failures one at a time.

Examples:

```text
wrong subnet mask
wrong default gateway
DNS misconfiguration
blocked TCP port
service listening only on localhost
bad route
VLAN mismatch
```

For each failure:

```text
1. State symptoms.
2. Form a hypothesis.
3. Choose evidence.
4. Run commands/capture packets.
5. Locate the failure.
6. Explain why it failed.
7. Fix it.
8. Verify the fix.
```

---

## Capstone Part 3 — Developer Request Journey

Run or model:

```text
Client
  ↓
HTTPS
  ↓
Reverse Proxy
  ↓
ASP.NET Core API
  ↓
PostgreSQL
```

Explain the network journey from start to finish.

Final artifact:

```text
capstone/final-report.md
```

---

# 6. Recommended Calendar

This is a suggested schedule, not a strict rule.

```text
Days 01–04   Phase 1
Day 05       Checkpoint 01

Days 06–09   Phase 2

Days 10–15   Phase 3
Day 16       Checkpoint 02 / repair

Days 17–23   Phase 4
Day 24       Checkpoint 03

Days 25–29   Phase 5

Days 30–32   Phase 6
Day 33       Checkpoint 04

Days 34–35   Developer networking

Days 36–38   Integrated troubleshooting

Days 39–40   Capstone / weak-topic repair
```

If progress is faster:

- combine short Missions
- reduce light-review days
- finish closer to Day 30–34

If an essential Mission is weak:

- use the extra days
- do not skip mastery to preserve the calendar

---

# 7. Spaced Review Schedule

Every important concept enters a review queue.

Default pattern:

```text
T0    — learn
T+1   — 1–3 recall questions
T+3   — short new scenario
T+7   — mixed challenge
T+14  — troubleshooting / explain-back
```

Weak concepts return sooner.

Strong concepts may be reviewed less often.

Examples of high-priority spaced topics:

```text
ARP
IPv4
subnetting
routing
TCP
DNS
NAT
VLANs
```

---

# 8. Visual Plan

Visuals should be intentionally associated with Missions.

High-value visual Missions:

```text
M03  Encapsulation
M04  OSI/TCP-IP
M05  Ethernet frame
M06  Switch forwarding
M07  ARP local vs remote
M09  IPv4 address structure
M10  Subnet boundaries
M12  Routing decision
M13  Packet across routers
M17  TCP handshake
M20  DNS resolution
M21  DHCP DORA
M22  NAT/PAT
M23  DNS → TCP → TLS → HTTP
M24  VLANs/trunks
M27  Firewall segmentation
M28  proxy/reverse proxy/load balancer
M34  container networking
Final Follow-the-Packet
```

Images should communicate one clear mental model.

Avoid decorative diagrams.

---

# 9. Repository Structure

Expected structure as the journey grows:

```text
network-learning-journey/
│
├── README.md
├── LEARNING_WORKFLOW.md
├── ROADMAP.md
├── PROGRESS.md
│
├── missions/
│   ├── 01-what-is-a-network/
│   ├── 02-hosts-and-interfaces/
│   ├── ...
│
├── labs/
│   ├── windows/
│   ├── linux/
│   ├── wireshark/
│   ├── packet-tracer/
│   └── docker/
│
├── captures/
├── images/
├── reviews/
├── checkpoints/
└── capstone/
```

Do not generate all Mission folders on day one.

Create them as they are reached.

The Git history should show the journey growing naturally.

---

# 10. Mission Repository Template

When a Mission needs repository artifacts, prefer:

```text
missions/07-arp/
├── README.md
├── lab.md
├── review.md
└── images/
```

Not every Mission needs every file.

Avoid documentation bureaucracy.

## README.md

May contain:

```text
Goal
Core mental model
Important concepts
Commands/tools
```

## lab.md

Contains:

```text
Prediction
Steps
Observation
Explanation
```

## review.md

Prefer learner-written language:

```text
What I learned
What I can explain
What I observed
What I still confuse
```

---

# 11. Checkpoint Rules

A checkpoint should not be a large multiple-choice test.

It should verify reasoning.

Use:

```text
Explain-back
Packet journey
New scenario
Small lab
Troubleshooting
```

At the end update mastery.

Example:

```text
ARP          5/6
IPv4         4/6
Subnetting   3/6
Routing      4/6
```

Do not mark weak topics as complete only because their Mission was visited.

---

# 12. Network+ Breadth Policy

Some Network+ objectives require recognition more than deep engineering skill.

Spend less time on:

```text
obscure connector memorization
historical physical technologies
minor certification terminology
deep wireless standard tables
vendor-specific trivia
```

Spend more time on:

```text
packet flow
IP
subnetting
routing
TCP/UDP
DNS
DHCP
NAT
switching
VLANs
firewalls
monitoring
troubleshooting
```

Before finishing the roadmap, perform a final N10-009 coverage review to identify certification-only gaps.

---

# 13. New Chat / Context Reset Protocol

The repository is the persistent memory.

A new ChatGPT conversation should require only:

```text
LEARNING_WORKFLOW.md
ROADMAP.md
PROGRESS.md
```

plus current Mission artifacts when useful.

Start prompt:

```text
Continue my Networking Learning Journey.

Read:
- LEARNING_WORKFLOW.md
- ROADMAP.md
- PROGRESS.md

Continue exactly from the current Mission and next incomplete Part.

Use simple English.
Follow the part-by-part learning workflow.
Do not restart previous material unless PROGRESS.md says it needs review.
```

This allows the learning journey to survive long conversations and context-window resets.

---

# 14. Final Graduation Criteria

The journey is successful when I can:

## Explain

```text
how a host decides local vs remote
how ARP works
how routing works
how TCP establishes and maintains a connection
how DNS resolves a name
how NAT changes traffic
how VLANs segment a LAN
how firewalls affect applications
```

## Observe

Using:

```text
Windows/Linux commands
Wireshark
Packet Tracer
Docker
```

## Troubleshoot

A realistic problem systematically.

## Transfer

Apply networking knowledge to:

```text
ASP.NET Core
databases
Docker
reverse proxies
cloud environments
microservices
future cybersecurity study
```

## Follow the Packet

Explain a complete application request from:

```text
application code
```

through:

```text
DNS
routing
link layer
TCP
TLS
HTTP
network infrastructure
server
database
```

and back.

That is the main graduation test.

---

# 15. Starting Point

Begin with:

```text
Mission 01 — What Is a Network?
```

Do not pre-create or pre-read later Missions.

Start the learning journey using the workflow in:

```text
LEARNING_WORKFLOW.md
```

At the end of the first session, initialize:

```text
PROGRESS.md
```

with the actual learning state.
