# Video Script: Akeyless Modern PAM vs HashiCorp Boundary

## Video Details
- **Title:** Akeyless Modern PAM vs HashiCorp Boundary: Why Unified Beats Fragmented
- **Duration:** ~10-11 minutes
- **Format:** Talking head + screen share (Akeyless demo)

---

## INTRO (0:00 - 1:00)

### On Camera

> "VPNs and bastion hosts are relics of a different era. If you're managing access to cloud infrastructure in 2024, you need something better -identity-based, zero-trust, with full auditability.
>
> Two names come up in this space: Akeyless Secure Remote Access and HashiCorp Boundary. Today I'm going to show you why these aren't really apples-to-apples -and why that matters for your organization.
>
> Stay until the end for a live demo of Akeyless in action. Let's dive in."

---

## SECTION 1: The Challenge with Boundary's Approach (1:00 - 2:30)

### On Camera / Show Boundary Editions Diagram

> "Let me start with HashiCorp Boundary. Boundary is an identity-aware proxy -it authenticates users and brokers connections to your infrastructure. Solid concept, and HashiCorp has done good work here.
>
> But here's what you need to know: Boundary comes in three editions, and the features you probably want? They're not in the free one."

### Show Feature Availability Chart

> "Community Edition gives you basic access brokering. But 'brokering' means users actually see and enter passwords. That's a security concern for most enterprises.
>
> **Credential injection** -where users never see passwords? That's only in HCP or Enterprise.
>
> **Session recording**? Also only in paid tiers. And even then, it only works for SSH connections.
>
> Plus, for secrets management and dynamic credentials, you need to add HashiCorp Vault. That's a whole separate product to deploy, configure, and maintain."

---

## SECTION 2: The Akeyless Difference (2:30 - 4:30)

### On Camera / Show Akeyless Platform Diagram

> "Akeyless took a fundamentally different approach. Instead of building one piece of the puzzle, they built the whole picture.
>
> Akeyless is a **unified Identity Security Platform**. Secrets management, privileged access, certificate management, encryption -it's all one product. And that's not just marketing speak; it means these capabilities work together natively."

### Show Key Differentiators Slide

> "Here's what you get with Akeyless out of the box, no premium tier required:
>
> **Credential injection by default.** Users authenticate once; Akeyless handles the rest. No one ever sees a password.
>
> **Comprehensive session recording.** For terminal sessions like SSH, databases, and Kubernetes, you get full transcripts of every command and output. For RDP sessions, you get complete video recordings. All of it can be exported to S3, Azure Blob, or your SIEM of choice like Splunk or Elasticsearch.
>
> **Native support for 9 resource types.** Not just SSH and TCP tunnels. Akeyless has purpose-built integrations for SSH, RDP, databases, Kubernetes, all three major cloud consoles, web applications, and RabbitMQ. One platform covers your entire infrastructure.
>
> **Zero-knowledge security.** This is huge. Akeyless uses something called Distributed Fragments Cryptography. Your secrets are never whole in any single location, not even Akeyless can access them. That's a level of security traditional vaults can't match."

---

## SECTION 3: Side-by-Side Comparison (4:30 - 5:30)

### Show Comparison Table

> "Let me put this in perspective with a direct comparison.
>
> | What You Need | Akeyless | Boundary Community | Boundary Paid |
> |---------------|----------|-------------------|---------------|
> | Passwordless access | Yes | No | Yes |
> | Session recording | Video (RDP) + Transcripts (terminal) | No | SSH only |
> | Secrets management | Built-in | Need Vault | Need Vault |
> | Kubernetes native | Yes | TCP only | TCP only |
> | Database native | Yes | TCP only | TCP only |
> | Web app access | Yes | No | No |
> | Cloud consoles (AWS/Azure/GCP) | Yes | No | No |
> | RabbitMQ | Yes | No | No |
> | Infrastructure needed | None | Self-managed | Varies |
>
> With Boundary, to get feature parity, you're looking at HCP or Enterprise licensing PLUS Vault. With Akeyless, everything is included in one platform."

---

## SECTION 4: Why This Matters for Your Team (5:30 - 6:30)

### On Camera

> "This isn't just about features on a spreadsheet. It's about what your team actually deals with day-to-day.
>
> With the HashiCorp approach, you're managing multiple products. Boundary for access, Vault for secrets, maybe Consul for discovery. Each one needs deployment, upgrades, monitoring, troubleshooting. That's operational overhead that compounds.
>
> With Akeyless, it's one platform. One deployment -actually, zero deployment because it's fully managed SaaS. One set of APIs. One vendor relationship. One place for your team to learn.
>
> And the unified architecture means things just work together. Create a dynamic secret, use it for privileged access, rotate it automatically when the session ends -all seamless, all in one place."

---

## SECTION 5: Akeyless Demo (6:30 - 9:30)

### Switch to Screen Share

> "Enough talk. Let me show you what this looks like in practice."

### Demo Flow:

**1. Platform Overview (30 seconds)**
> "Here's the Akeyless console. Notice how secrets management and secure remote access are in the same platform. This isn't stitched together, it's built as one product."

**2. SSH Access with Credential Injection (1 minute)**
> "Let's connect to a Linux server. I'm setting up SSH access using a rotated secret, credentials that automatically change after my session ends.
>
> Watch what happens when I connect... I click, I authenticate, and I'm in. No password prompt. Akeyless retrieved the credential, injected it into the session, and established the connection. I never saw or touched the password."

**3. SSH Session Recording (30 seconds)**
> "Everything I just did was recorded. Let me show you the session transcript. You can see every command I entered and every output. This transcript data can be forwarded to Splunk, Elasticsearch, or Syslog for your compliance and monitoring workflows."

**4. RDP Access to Windows Server (1 minute)**
> "Now let's look at Windows. I'm going to connect to a Windows server via RDP. Same concept: I authenticate to Akeyless, and the credentials are injected automatically.
>
> Notice I'm connected to a full Windows desktop session. No password entry, no credential exposure. And you see that indicator? That tells the user this session is being recorded. Admins can toggle that off if needed."

**5. RDP Video Recording Playback (45 seconds)**
> "Here's where RDP recording gets interesting. Unlike terminal sessions that capture text transcripts, RDP sessions are recorded as video. Let me show you a previous session playback.
>
> You can scrub through the entire session, see exactly what the user did on the Windows server. These recordings can be stored locally, or automatically uploaded to S3 or Azure Blob Storage. You can also enable AES encryption and compression for security and storage efficiency."

**6. Sessions Overview Dashboard (30 seconds)**
> "From the admin side, I have full visibility into all sessions. I can see who's connected, what resources they're accessing, session duration, and status. This view auto-refreshes every 20 seconds, and I can filter by resource type, gateway, or user. Everything is logged for your audit trail."

**7. Kubernetes Access (30 seconds)**
> "Quick look at Kubernetes. Traditional approach: manage kubeconfig files, distribute certificates, deal with expiration. With Akeyless: I click connect, authenticate, and I have kubectl access to my cluster. Certificates handled behind the scenes, rotated automatically."

---

## OUTRO (9:30 - 10:30)

### On Camera

> "Look, HashiCorp makes solid tools. Boundary solves real problems. But for most organizations, the question isn't 'Is Boundary good?' It's 'Do I want to manage multiple products and deal with feature limitations, or do I want everything in one platform?'
>
> Akeyless gives you enterprise-grade PAM -credential injection, full session recording, native support for modern workloads -without the complexity of stitching together multiple products.
>
> If that sounds like what you need, check out the links in the description. Akeyless offers demos and free trials so you can see this for yourself.
>
> Thanks for watching. If you found this useful, hit subscribe. Drop a comment if you have questions or want me to cover something specific. See you in the next one."

---

## Supporting Materials Needed

### Slides/Graphics:
1. Boundary editions diagram (Community → HCP → Enterprise)
2. Feature availability by Boundary edition
3. Akeyless unified platform architecture
4. Key differentiators slide (4 bullet points)
5. Side-by-side comparison table
6. TCO comparison visual

### Demo Prerequisites:
- Akeyless account with SRA configured
- Linux target server with rotated SSH credentials
- Windows target server for RDP demo
- Kubernetes cluster with Akeyless integration
- Pre-recorded SSH session transcript for playback
- Pre-recorded RDP video session for playback
- RDP recording storage configured (S3 or Azure Blob)

### Links for Description:
- Akeyless Demo Request: https://www.akeyless.io/demo/
- Akeyless SRA Docs: https://docs.akeyless.io/docs/remote-access-overview
- Blog post: [link to published blog]

---

## Key Messages to Emphasize

1. **Unified beats fragmented** - One platform eliminates tool sprawl and operational overhead
2. **Enterprise features included** - No paywalled functionality for critical capabilities
3. **9 native resource types** - SSH, RDP, databases, Kubernetes, AWS/Azure/GCP consoles, web apps, RabbitMQ
4. **Zero-knowledge security** - DFC provides security guarantees competitors can't match
5. **Zero infrastructure** - Fully managed SaaS means nothing to deploy or maintain

## Tone Guidelines

- **Confident but not dismissive**  - Acknowledge Boundary is a legitimate tool
- **Focus on Akeyless strengths**  - Lead with what Akeyless does well rather than attacking competitors
- **Practical, not theoretical**  - Emphasize real-world impact for teams
- **Let the demo speak**  - The product demonstration is the strongest argument
