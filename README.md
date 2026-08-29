# CCNP CML Labs

Hands-on Cisco Certified Network Professional (CCNP) practice labs built for Cisco Modeling Labs (CML).

This repository will grow into a collection of reusable CCNP labs. Each lab includes an importable CML topology and a companion guide covering the objectives, configuration tasks, verification commands, troubleshooting workflow, and completion criteria.

## Available labs

| Lab | Exam area | Topic | Nodes |
| --- | --- | --- | --- |
| [01 - IEEE 802.1Q Trunk](labs/01-802.1q-trunk/) | CCNP ENCOR | Configure and verify a static 802.1Q trunk | SW1, SW2, PC1, PC2 |
| [02 - Secure SSH Management](labs/02-secure-ssh-management/) | CCNP ENCOR | Secure router management with local users, SSHv2, and VTY authentication | R1, PC1 |
| [03 - Single-Area OSPFv2](labs/03-single-area-ospfv2/) | CCNP ENCOR | Configure area 0 across a three-router full mesh and verify complete route exchange | R1, R2, R3 |

## Repository structure

```text
ccnp-cml-labs/
├── README.md
└── labs/
    ├── 01-802.1q-trunk/
    │   ├── CCNP_ENCOR_-_802.1Q_Trunk_Practice.yaml
    │   └── CCNP_ENCOR_802.1Q_Trunk_KB.docx
    ├── 02-secure-ssh-management/
    │   ├── CCNP_ENCOR_-_Secure_SSH_Management_Practice.yaml
    │   ├── CCNP_ENCOR_Secure_SSH_Management_KB.docx
    │   └── CCNP_ENCOR_Secure_SSH_Management_Topology.png
    └── 03-single-area-ospfv2/
        ├── CCNP_ENCOR_-_Single-Area_OSPFv2_Practice.yaml
        ├── CCNP_ENCOR_Single_Area_OSPFv2_KB.docx
        └── CCNP_ENCOR_Single_Area_OSPFv2_Topology.png
```

Each numbered lab directory contains:

- A `.yaml` file that can be imported into Cisco CML.
- A `.docx` lab guide with the exercise, commands, verification steps, and troubleshooting material.
- A topology image when one is available for the lab.

## Requirements

The current labs were created and validated with:

- Cisco Modeling Labs 2.10
- Cisco IOSvL2 2020 image (`iosvl2-2020`)
- Cisco IOSv 15.9(3)M12 image (`iosv-159-3-m12`)
- CML Net-Tools container image (`net-tools-2-10-1-3`)

Image definition names must match those referenced by the imported topology. If your CML server uses different names, select the corresponding installed images after importing the lab.

## Importing a lab into CML

1. Download the desired lab's `.yaml` file.
2. Sign in to Cisco CML.
3. Choose **Import Lab** and select the YAML file.
4. Confirm that each node is mapped to an installed image definition.
5. Open the companion Word guide before starting the topology.
6. Start the nodes and complete the configuration and verification tasks.

## Lab 01: IEEE 802.1Q Trunk

The first lab provides a four-node topology for configuring and verifying a static 802.1Q trunk between two IOSvL2 switches.

The base configuration includes:

- VLAN 10 for user hosts.
- VLAN 20 for server traffic.
- VLAN 99 for switch management and the native VLAN exercise.
- PC1 and PC2 addressing.
- Access-port and management SVI configuration.
- An intentionally unconfigured inter-switch trunk for the learner to complete.

The lab guide includes configuration examples, operational verification, end-to-end testing, fault-injection exercises, and an ENCOR-level troubleshooting workflow.

## Lab 02: Secure SSH Management

The second lab provides a directly connected router and management client for configuring secure remote CLI access to Cisco IOS.

The base configuration includes:

- R1 address `192.168.10.1/24` on GigabitEthernet0/0.
- PC1 address `192.168.10.10/24` with R1 as its default gateway.
- Working console access and IP connectivity.
- SSH, local users, RSA keys, and VTY authentication intentionally left unconfigured for the learner.

The exercise covers a privilege-15 local user, a 2048-bit RSA identity key, SSH version 2, local VTY authentication, SSH-only inbound transport, idle-session timeouts, Telnet rejection, operational verification, client compatibility, optional login hardening, and fault-injection practice.

## Lab 03: Single-Area OSPFv2

The third lab provides a full-mesh triangle of three IOSv routers for configuring and verifying OSPFv2 in area 0.

The base configuration includes:

- Three addressed `/30` transit networks connecting R1, R2, and R3.
- A `/32` Loopback0 address on each router for the OSPF router ID and end-to-end testing.
- Interface descriptions, enabled routed links, and working direct connectivity.
- OSPF intentionally left unconfigured for the learner.

The exercise covers OSPF process 10, explicit router IDs, precise network statements, passive loopback interfaces, neighbor and interface verification, LSDB inspection, complete route exchange, source-specific loopback testing, troubleshooting workflows, and optional reconvergence and path-cost challenges.

## Roadmap

Additional CCNP labs will be added as new topics are completed. The numbered directory format keeps the collection ordered while allowing each lab to remain self-contained.

## Cisco software notice

This repository contains lab definitions and original documentation only. Cisco virtual machine images are not included. Users must obtain and license Cisco software through the appropriate Cisco channels.
