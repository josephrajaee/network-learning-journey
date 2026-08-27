# Network Learning Journey

An AI-assisted, mission-based networking learning journey focused on **real understanding, hands-on practice, troubleshooting, and software-engineering relevance**.

This repository is my persistent learning workspace for studying computer networking from fundamentals to a strong practical Network+ level, with additional focus on backend development, Linux, Docker, packet analysis, and real-world troubleshooting.

---

## Goal

The main goal is not simply:

> Pass CompTIA Network+.

The main goal is:

> Understand how computer networks actually work well enough that networking is no longer a black box when building, deploying, debugging, or operating software systems.

I want to be able to reason about questions such as:

```text
What happens when an application sends an HTTP request?
How does DNS resolution happen?
How does the OS choose a route?
Why does ARP happen?
What changes at each router hop?
How does TCP establish a connection?
Where does TLS happen?
How do reverse proxies and load balancers affect traffic?
Why does a database connection time out?
Why can DNS work while TCP fails?
How do Docker containers communicate?
How do I prove where a network problem is?
```

---

## Learning Style

This journey is designed around:

```text
Mission-based learning
Part-by-part teaching
Prediction before observation
Explain-back
Visual learning
Hands-on labs
Wireshark
Packet Tracer
Troubleshooting
Spaced review
Mastery tracking
Checkpoints
Capstone
```

The learning workflow is defined in:

```text
LEARNING_WORKFLOW.md
```

The full roadmap is defined in:

```text
ROADMAP.md
```

The current learning state is stored in:

```text
PROGRESS.md
```

---

## Duration

Target:

```text
30–40 days
```

Recommended daily time:

```text
Standard session: 60–90 minutes
Minimum session: 20 minutes
```

The calendar is flexible.

A difficult Mission can take longer if needed.

The goal is mastery, not rushing through day numbers.

---

## Current Progress

Current starting point:

```text
Mission 01 — What Is a Network?
Status: NOT_STARTED
```

Detailed progress is tracked in:

```text
PROGRESS.md
```

---

## Roadmap

The journey is organized into these phases:

```text
Phase 1 — Network Mental Model
Phase 2 — Ethernet, MAC and Local Delivery
Phase 3 — IPv4, Subnetting and Routing
Phase 4 — Transport and Application Services
Phase 5 — LAN Infrastructure and Security
Phase 6 — Operations, Physical and Modern Networking
Phase 7 — Developer / Linux / Container Networking
Phase 8 — Troubleshooting and Packet Analysis
Phase 9 — Integrated Capstone
```

The roadmap contains:

```text
34 core Missions
4 Checkpoints / Repair sessions
Integrated troubleshooting sessions
Final capstone
```

---

## Core Learning Loop

Important topics follow this loop:

```text
Problem
   ↓
Simple Mental Model
   ↓
Prediction
   ↓
Learn
   ↓
Explain Back
   ↓
Visual
   ↓
Lab
   ↓
Observe
   ↓
Compare Prediction vs Reality
   ↓
Troubleshoot
   ↓
Transfer Challenge
   ↓
Mastery Gate
   ↓
Review
```

This repository is designed to produce evidence of understanding, not only notes.

---

## Follow the Packet

A recurring challenge throughout the journey is:

```text
Follow the Packet
```

As knowledge grows, I repeatedly revisit an application request:

```text
.NET HttpClient
      ↓
DNS
      ↓
Route Lookup
      ↓
ARP / Neighbor Resolution
      ↓
Ethernet / Wi-Fi
      ↓
Switch
      ↓
Router
      ↓
NAT
      ↓
Internet
      ↓
TCP
      ↓
TLS
      ↓
HTTP
      ↓
Reverse Proxy / Load Balancer
      ↓
Kestrel
      ↓
ASP.NET Core
      ↓
PostgreSQL
```

The final goal is to explain this journey clearly from application code down to the network and back.

---

## Repository Structure

The repository grows naturally as the learning journey progresses.

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
│   └── ...
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

Mission folders are created only when they are reached.

The Git history should reflect the actual learning journey.

---

## Mission Structure

A Mission may contain:

```text
README.md
lab.md
review.md
images/
```

Not every Mission needs every file.

The repository should stay useful, not bureaucratic.

Example:

```text
missions/07-arp/
├── README.md
├── lab.md
├── review.md
└── images/
```

---

## Labs

The journey uses real networking tools.

### Windows

```text
ipconfig
arp
route
ping
tracert
nslookup
netstat

Get-NetAdapter
Get-NetIPAddress
Get-NetRoute
Get-NetTCPConnection
Resolve-DnsName
Test-NetConnection
```

### Linux / WSL

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

### Networking Tools

```text
Wireshark
Packet Tracer
Docker
```

---

## Packet Captures

Important protocols are observed instead of only memorized.

Examples:

```text
ARP
ICMP
DNS
TCP
TLS
HTTP
DHCP
```

Packet captures may be stored in:

```text
captures/
```

Example:

```text
captures/arp-request-reply.pcapng
captures/tcp-three-way-handshake.pcapng
captures/dns-query-response.pcapng
```

---

## Visual Learning

Important networking concepts are supported with diagrams and generated visuals.

Examples:

```text
encapsulation
OSI / TCP-IP
switch forwarding
ARP
IPv4 subnet boundaries
routing decisions
TCP handshake
DNS resolution
NAT
VLANs
firewalls
reverse proxies
container networking
```

Visual assets live under:

```text
images/
```

or inside the relevant Mission.

---

## Mastery

Progress is based on ability, not content consumed.

```text
Level 0 — Unknown
Level 1 — Recognize
Level 2 — Understand
Level 3 — Explain
Level 4 — Apply
Level 5 — Analyze / Troubleshoot
Level 6 — Transfer
```

Core networking concepts should usually reach:

```text
Level 5–6
```

Lower-priority certification topics may stop earlier.

---

## Review System

Important concepts return through spaced retrieval.

Default pattern:

```text
T0    — Learn
T+1   — Quick recall
T+3   — New scenario
T+7   — Mixed challenge
T+14  — Troubleshooting / explain-back
```

Weak topics are reviewed more frequently.

---

## Checkpoints

Every few Missions, a checkpoint combines previous knowledge.

A checkpoint can contain:

```text
Recall
Packet journey
Small lab
Troubleshooting
Transfer scenario
Mastery update
```

Checkpoint artifacts are stored under:

```text
checkpoints/
```

---

## Troubleshooting Philosophy

Networking is not learned only through successful examples.

The workflow intentionally includes broken scenarios such as:

```text
wrong subnet mask
wrong gateway
DNS failure
closed TCP port
firewall block
routing failure
VLAN mismatch
service listening only on localhost
packet loss
```

The process is:

```text
Symptom
  ↓
Hypothesis
  ↓
Evidence
  ↓
Test
  ↓
Locate failure
  ↓
Explain
  ↓
Fix
  ↓
Verify
```

---

## Backend Developer Perspective

Networking concepts are frequently connected to software engineering.

Examples include:

```text
ASP.NET Core
HttpClient
Kestrel
PostgreSQL
Redis
REST APIs
Docker
Nginx
reverse proxies
load balancers
microservices
cloud networking
```

A recurring question is:

> Why does this networking concept matter to a backend developer?

---

## Using This Repository With ChatGPT

This repository is the persistent memory of the learning journey.

Chat history is not the source of truth.

When starting a new ChatGPT session, the important files are:

```text
LEARNING_WORKFLOW.md
ROADMAP.md
PROGRESS.md
```

Then use a prompt similar to:

```text
Continue my Networking Learning Journey.

Read:
- LEARNING_WORKFLOW.md
- ROADMAP.md
- PROGRESS.md

Continue exactly from the current Mission and next incomplete Part.

Use simple English.
Teach one part at a time.
Follow the learning workflow.
Do not restart previous material unless PROGRESS.md says it needs review.
```

This allows the journey to continue even when previous conversations become long or context-heavy.

---

## Session Workflow

A typical session looks like:

```text
Open PROGRESS.md
      ↓
Quick spaced review
      ↓
Continue current Mission
      ↓
Learn one small Part
      ↓
Predict / answer
      ↓
Visual
      ↓
Lab
      ↓
Observe
      ↓
Troubleshoot
      ↓
Review
      ↓
Update PROGRESS.md
      ↓
Git commit
```

---

## Git History as Learning History

Commits should represent meaningful learning progress.

Examples:

```text
learn(arp): understand ARP resolution
lab(arp): capture ARP request and reply
learn(routing): understand default gateway selection
lab(tcp): inspect three-way handshake
review(core): complete networking checkpoint
fix(concept): correct destination MAC mental model
```

The repository history becomes a timeline of the learning journey.

---

## Network+ Coverage

The roadmap uses the current CompTIA Network+ N10-009 objectives as a coverage reference.

Official domain weights:

```text
Networking Concepts       23%
Network Implementation    20%
Network Operations        19%
Network Security          14%
Network Troubleshooting   24%
```

The roadmap intentionally spends more practical time on fundamentals and troubleshooting than on certification trivia.

---

## Certification vs Real Understanding

High-priority topics:

```text
packet flow
Ethernet
ARP
IPv4
subnetting
routing
ICMP
TCP / UDP
DNS
DHCP
NAT
switching
VLANs
firewalls
Wireshark
troubleshooting
```

Lower-priority memorization topics are still covered when needed for Network+, but they should not dominate study time.

---

## Capstone

The journey ends with an integrated network lab.

The capstone should combine:

```text
IP addressing
subnetting
switching
VLANs
routing
DNS
DHCP
NAT
firewalls
TCP
TLS
HTTP
Docker / application networking
troubleshooting
```

The learner must diagnose intentionally broken scenarios using evidence.

Final documentation belongs under:

```text
capstone/
```

---

## Definition of Success

The journey is complete when I can receive a realistic networking problem and reason through it systematically.

Example:

```text
An ASP.NET Core application cannot connect
to PostgreSQL on another server.
```

I should be able to investigate:

```text
interface
IP address
subnet
route
ARP / neighbor
gateway
DNS
firewall
TCP port
service listener
application configuration
```

using commands, packet captures, and clear reasoning.

The final goal is not:

```text
I finished 34 Missions.
```

The final goal is:

> I understand how networks work, can observe real network behavior, and can troubleshoot problems using evidence.

---

## Start Here

Read:

```text
LEARNING_WORKFLOW.md
ROADMAP.md
PROGRESS.md
```

Then begin:

```text
Mission 01 — What Is a Network?
```
