# -VLANs-Routing-Enterprise-Management(Cisco Packet Tracer)

Overview

Designed and implemented a segmented enterprise network in Cisco Packet Tracer to reinforce Network+ and CCNA-aligned networking fundamentals, with a focus on real-world troubleshooting and verification rather than scripted success.

Figure 0 – Network Architecture Overview
<img width="1386" height="782" alt="image" src="https://github.com/user-attachments/assets/b1eab299-6995-4a8d-adfe-40bed6931661" />

Logical network topology showing segmented VLAN design with router-on-a-stick routing, access and distribution switches, DMZ and management servers, and isolated user groups.

Figure 1 – VLAN Design & Segmentation
<img width="1084" height="458" alt="image" src="https://github.com/user-attachments/assets/209c8635-0635-4154-8e05-94177ff4e661" />

Verified VLAN creation and access-port assignment using show vlan brief, confirming correct segmentation and server placement in DMZ (VLAN 30) and Management (VLAN 99).

Figure 2 — 802.1Q Trunk Configuration & Verification
<img width="1132" height="277" alt="image" src="https://github.com/user-attachments/assets/8cf141ea-83f3-46de-afe9-8a72e478f40a" />

Verified 802.1Q trunk configuration and allowed VLANs between switches using show interfaces trunk, confirming VLAN propagation across the network.

Figure 3 – STP Trunk Inconsistency Encountered
<img width="1929" height="1301" alt="image" src="https://github.com/user-attachments/assets/33d1d8bc-884e-478f-abe1-81ffedc7c605" />

Encountered an STP PVID inconsistency caused by mismatched trunk configuration, resulting in temporary port blocking. Issue was resolved by aligning trunk modes and allowed VLANs across switches.

Figure 4 — Centralized Logging & Time Synchronization
<img width="746" height="117" alt="image" src="https://github.com/user-attachments/assets/da307c31-c631-4469-a295-c6b829d43b77" />

Verified centralized Syslog and NTP configuration on the router using show running-config, confirming integration with the management server for monitoring and time synchronization.
Figure 5 — Layer 2 / Management VLAN Troubleshooting & Validation

During implementation, I encountered multiple Layer 2–related issues while validating trunking and management access across switches.

Issue Observed

Switch ports intermittently transitioned between up/down

Management VLAN (VLAN 99) initially appeared down/down

Cisco IOS generated Spanning Tree Protocol (STP) PVID inconsistency messages when trunking was introduced

Verification commands failed when executed from incorrect IOS configuration modes

These symptoms indicated a mismatch between port mode configuration, VLAN assignment, and STP expectations on interconnected switch ports.

Resolution

Once trunk and access port configurations were aligned:

STP stabilized and stopped blocking interfaces

VLAN 99 transitioned to up/up

Trunk links successfully passed all required VLANs (10, 20, 30, 40, 99)

Layer 2 forwarding normalized across the topology

This confirmed the network was ready for Layer 3 inter-VLAN routing, which was validated in the subsequent step.

Figure 6 - Inter-VLAN Routing Verification
<img width="818" height="714" alt="image" src="https://github.com/user-attachments/assets/9a34a3cd-eede-4b2b-9458-5a8d536b71df" />

Verified router-on-a-stick configuration with multiple VLAN subinterfaces in an up/up state using show ip interface brief, confirming successful inter-VLAN routing.


Appendix A — Completed Network Topology
<img width="800" height="482" alt="image" src="https://github.com/user-attachments/assets/f327b2c6-9a6c-4871-9f54-b7566c02828c" />

This figure represents the final operational state of the network after completing VLAN segmentation, trunk configuration, Layer 2 troubleshooting, and inter-VLAN routing.

The topology view confirms:

All network devices are powered on and operational

Physical and logical connectivity is fully established

Inter-switch trunk links are active

End hosts and infrastructure components are correctly integrated into the topology

This visual serves as a high-level confirmation that the network is stable following configuration and verification steps shown in subsequent figures.

While detailed validation is demonstrated through CLI outputs (VLAN status, trunking, routing, and services), this topology view provides an at-a-glance representation of the completed, functional network design.
