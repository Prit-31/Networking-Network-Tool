# My Wireshark Practice Log

## 1. Captured Network Traffic
- Selected my active Wi-Fi interface.
- Started and stopped packet capture after browsing a website.
- Saved the capture file as `myfirstcapture.pcap`.

## 2. Used Filters to Search Packets
- Filtered HTTP traffic using `http` filter.
- Filtered DNS queries with `dns`.
- Found ping requests using `icmp`.
- Filtered packets to/from my laptop’s IP: `ip.addr == 192.168.1.10`.
- Filtered HTTP traffic to a specific server: `http && ip.dst == 203.0.113.5`.

## 3. Followed TCP Streams
- Right-clicked on a TCP packet and selected “Follow TCP Stream.”
- Analyzed the entire HTTP conversation between my laptop and the server.

## 4. Inspected Packets in Detail
- Expanded packet details to understand each protocol layer.
- Viewed raw data bytes of selected packets.

## 5. Used Statistics Tools
- Checked Protocol Hierarchy to see traffic breakdown.
- Viewed Endpoints to see all devices involved.
- Used I/O Graphs to visualize traffic spikes during browsing.

## 6. Identified Errors and Anomalies
- Applied `tcp.analysis.flags` filter to spot potential TCP issues.
- Filtered large frames using `frame.len > 1500`.

## 7. Practiced with Real-World Traffic
- Captured web browsing, DNS lookups, and ping requests.
- Followed TCP streams for HTTP GET and POST requests.
- Analyzed responses and packet exchanges.

---

This log shows the practical skills I developed while learning Wireshark step-by-step.
