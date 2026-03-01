# 🌌 Realm: The Entropy Law Engine

> "We observe the physics of the network, not just the signatures. Your server, your sovereignty."

Realm is a next-generation, ultra-lightweight network defense engine built on eBPF (XDP) and Shannon Entropy. Deployed at the deepest layer of the Linux kernel (Ring 0), it calculates the microscopic thermodynamic properties of network packets in real-time, physically severing unknown threats and 0-day attacks in nanoseconds.

## 👁️ Why Realm? (A Reflection on the Industry)

The cybersecurity landscape has long suffered from traditional, bloated security software.

1. **Lagging Signature Matching:** Traditional WAFs and Antivirus software are always one step behind hackers. They rely on massive "virus databases" or rigid Regex rules. Faced with mutated payloads or novel 0-day vulnerabilities, they are virtually blind.
2. **Suffocating Bloat:** To stack features, security agents often consume excessive CPU and memory resources, sometimes dragging down the very business operations they are meant to protect.
3. **Loss of Sovereignty & Privacy:** This is the most intolerable aspect. Many commercial security tools, under the guise of "Cloud Threat Intelligence," recklessly upload your server's raw traffic, logs, and even full PCAPs to their centralized servers. **You are paying for a black box that constantly surveils you.**

## 🏰 Core Philosophy: Local-First

In this cloud-native era where data is arbitrarily harvested, Realm firmly embraces the **Local-First** philosophy.

* **Absolute Data Privacy:** Realm operates at the NIC driver layer (XDP). All traffic observation, baseline calculation (EWMA), and interception judgments are completed in a closed loop within your local machine's memory. **Not a single byte of user data leaves your NIC. Your data belongs only to you.**
* **Dimensional Strike via Entropy:** We do not extract signature codes. The injection of malicious code, the establishment of encrypted tunnels, or the probing of overflow attacks—these behaviors inevitably cause violent fluctuations in the "Information Entropy" of network packets. Realm acts like a physicist, capturing this "tension" via Shannon Entropy to physically fuse threats the moment they erupt.
* **Kernel-Level Transparency:** As a privileged program running at Ring 0, trust is paramount. Realm's core logic is 100% open-source, completely transparent, and welcomes source code audits from the global community.

## ⚙️ Dynamic Laws & Adversarial Environments

Every server's network environment is unique. To ensure Realm perfectly adapts to your local ecosystem, we designed a **Dynamic Parameter Injection Mechanism**.

While the code is open-source, the "Threshold Laws" that dictate life and death are controlled by the deployer. You can dynamically inject golden parameters optimized for your specific environment via environment variables (\`REALM_DIVIDER\` and \`REALM_MULTIPLIER\`). **The ultimate interpretation of the Law always remains in the hands of the deployer.**

## ⚖️ License & Commercial Baseline (AGPL-3.0)

Realm adopts the strictest open-source license: **GNU AGPL v3.0**.

We welcome all geeks, researchers, and enterprises to download, use, and modify Realm for internal defense. However, we draw a hard line for cloud vendors attempting to free-ride on open-source efforts:
**If you intend to package Realm into your commercial SaaS product, or provide Realm-based protection services to third parties over a network, you MUST open-source your entire project and retain the original author's copyright and attribution.**

You may take our framework, but you must respect the open-source contract.

---

## 🚀 Quick Start

Realm is extremely lightweight with minimal dependencies. Unfold the barrier directly on your Linux server.

\`\`\`bash
# 1. Clone the repository
git clone https://github.com/xingkong0508/realm.git
cd realm

# 2. Compile eBPF probes (requires clang)
go generate ./...

# 3. Basic Mode (Uses community-default degraded parameters)
sudo /snap/bin/go run .

# 4. Sovereign Mode (Inject your private Law parameters tuned for your environment)
# NOTE: The values below are dummy examples. Replace them with your actual optimized parameters.
REALM_DIVIDER=0.888 REALM_MULTIPLIER=1.333 sudo -E /snap/bin/go run .
\`\`\`

In this dark forest of unknown threats, let us use the certainty of mathematics to guard our final server sovereignty.
