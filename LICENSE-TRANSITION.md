# License Transition: AGPL-3.0 → Apache 2.0

**Status:** Planning Phase  
**Target Completion:** Q1 2026  
**Last Updated:** December 2025

---

## 🎯 Executive Summary

Openwater is transitioning from **AGPL-3.0 to Apache 2.0** for all software and firmware, while adopting **CERN-OHL-P** for hardware designs. This change is essential for clinical translation, academic partnerships, and commercial ecosystem development.

**Bottom Line:** AGPL licensing prevents our platform from being used in clinical settings and blocks integration with the medical imaging community. Apache 2.0 removes these barriers while maintaining open-source principles.

---

## 📋 Why We're Making This Change

### The 3D Slicer Rejection: Critical Evidence

**What Happened:**
- We submitted `SlicerOpenLIFU` as an extension to 3D Slicer
- 3D Slicer community rejected it due to AGPL-3.0 licensing
- Their feedback: "Permissive licenses are the standard in medical image computing because **restrictive licenses practically prevent translating prototypes into clinical use**"

**Impact:**
- Blocked integration with the world's most widely used medical imaging platform
- Cannot reach 1000+ institutions using 3D Slicer
- Prevented collaboration with established medical imaging community
- Signaled broader issues with AGPL in healthcare

**This rejection provided the evidence we needed to advocate for license transition with our board.**

### Medical Device Ecosystem Requirements

**Why Apache 2.0 is Standard in Medical Imaging:**

1. **Clinical Translation Requirements**
   - Hospitals need ability to modify and deploy without source disclosure
   - Healthcare IT departments require flexibility for integration
   - Regulatory submissions (FDA, CE) require proprietary modifications
   - HIPAA compliance requires custom security implementations

2. **Academic Research Partnerships**
   - Universities need freedom to publish without source disclosure
   - Research grants often prohibit AGPL-licensed dependencies
   - Collaboration requires compatible licensing with other projects
   - Patent offices require freedom to operate

3. **Commercial Ecosystem Development**
   - Medical device OEMs cannot integrate AGPL components
   - Contract manufacturers need proprietary build processes
   - Cloud service providers require permissive licensing
   - Distribution partners need flexible terms

4. **Community Growth**
   - Most medical imaging projects use Apache 2.0 or BSD
   - Contributors prefer permissive licenses for career reasons
   - Integration with existing tools requires compatible licensing
   - Reduces legal friction for participation

### Industry Standards

**Medical imaging open-source projects using permissive licenses:**
- 3D Slicer: BSD-style license
- OHIF (Open Health Imaging Foundation): MIT license
- MONAI (Medical Open Network for AI): Apache 2.0
- PyTorch Medical: BSD license
- ITK (Insight Toolkit): Apache 2.0
- VTK (Visualization Toolkit): BSD license
- DCMTK (DICOM Toolkit): Modified BSD license

**AGPL is virtually non-existent in medical device open source.**

---

## 🔄 What's Changing

### Software & Firmware: AGPL-3.0 → Apache 2.0

**Repositories being relicensed:**

#### OpenLIFU Platform
- `OpenLIFU-python` - Core Python toolbox
- `SlicerOpenLIFU` - 3D Slicer extension (enables resubmission)
- `OpenLIFU-3DScanner` - Photogrammetry application
- `lifu-transmitter-fw` - Transmitter firmware
- `opw_ustx` - Ultrasound transmit module
- `st-ustx3_1-tx` - STM32 transmit firmware
- All other OpenLIFU software/firmware

#### OpenMOTION Platform
- `OpenMOTION-Pylib` - Python communication library
- `motion-sensor-fw` - Motion sensor firmware
- `motion-console-fw` - Console firmware
- `ow-bloodflow-app` - Blood flow application
- `opw_bloodflow_gen1_sw` - Generation 1 software
- All other OpenMOTION software/firmware

#### Infrastructure
- `openwater-commons` - This repository
- `openwater-docs` - Documentation site
- `awesome-openwater` - Curated resources
- All future software repositories

**Total:** ~25-30 repositories transitioning to Apache 2.0

### Hardware: AGPL-3.0 → CERN-OHL-P

**New hardware repositories using CERN Open Hardware License - Permissive:**
- `OpenLIFU-hardware-mechanical` - CAD files, 3D models
- `OpenLIFU-hardware-electrical` - Schematics, PCB layouts
- `OpenLIFU-bom` - Bill of materials
- `OpenMOTION-hardware-mechanical` - Motion hardware designs
- `OpenMOTION-hardware-electrical` - Motion electrical designs
- `OpenMOTION-bom` - Motion BOM

**Why CERN-OHL-P:**
- Designed specifically for hardware open source
- Permissive variant allows commercial use
- Industry standard for open hardware
- Compatible with Apache 2.0 software
- Used by Arduino, RISC-V, and other major projects

### Documentation: Stays CC-BY-4.0

**Already permissive:**
- `openwater-docs` - Creative Commons Attribution 4.0
- All documentation, tutorials, guides
- Assembly instructions
- Training materials

---

## 📝 License Comparison

### AGPL-3.0 (Current)

**Key Restrictions:**
- ❌ Network use triggers source disclosure ("AGPL loophole closure")
- ❌ Any modifications must be released under AGPL
- ❌ SaaS/cloud services must disclose source
- ❌ Cannot combine with proprietary software
- ❌ Incompatible with most medical device workflows

**Why It Made Sense Initially:**
- Protected against exploitation
- Ensured contributions flow back
- Strong copyleft for community protection

**Why It's Problematic Now:**
- Blocks clinical deployment (hospitals can't use)
- Prevents academic research (universities reject)
- Stops OEM partnerships (manufacturers can't integrate)
- Limits community growth (developers avoid)
- Rejected by medical imaging community

### Apache 2.0 (Target)

**Key Freedoms:**
- ✅ Use for any purpose (including commercial)
- ✅ Modify without disclosure requirements
- ✅ Distribute modified versions
- ✅ Combine with proprietary software
- ✅ Deploy in clinical settings
- ✅ Patent grant protection

**Benefits for Openwater:**
- Enables 3D Slicer integration
- Allows academic partnerships
- Permits OEM licensing
- Encourages community growth
- Compatible with medical device workflows

**Protections We Keep:**
- Patent grants protect contributors
- Attribution requirements preserved
- Trademark rights maintained
- Notice requirements ensure credit
- Liability disclaimers protect project

---

## 🛡️ What We're NOT Losing

### Myth: "Permissive = Companies Can Steal Our Work"

**Reality: We maintain strong protections:**

1. **Patent Pledge**
   - All 68 Openwater patents remain freely licensed
   - Patent grant in Apache 2.0 protects contributors
   - Cannot patent community contributions

2. **Trademark Protection**
   - "Openwater" trademark protected
   - "Open-LIFU™" trademark protected
   - "Open-Motion™" trademark protected
   - Cannot claim official Openwater products without permission

3. **Attribution Requirements**
   - Apache 2.0 requires attribution
   - Notice files must be preserved
   - Contributors recognized
   - Cannot remove copyright notices

4. **Ecosystem Control**
   - We control the canonical repositories
   - We set quality standards
   - We define the roadmap
   - We manage the community

5. **First-Mover Advantage**
   - Network effects favor the original
   - Community coalesces around our repos
   - Brand recognition and trust
   - Reference implementations

### Myth: "We Won't Get Contributions Back"

**Reality: Strong incentives for contribution:**

1. **Maintenance Burden**
   - Forks require ongoing maintenance
   - Easier to contribute upstream than maintain fork
   - Community bug fixes benefit everyone

2. **Collaboration Benefits**
   - Access to community expertise
   - Participation in roadmap decisions
   - Recognition and reputation
   - Career advancement opportunities

3. **Network Effects**
   - Value in being part of main project
   - Access to ecosystem tools
   - Community support and documentation
   - Interoperability advantages

**Examples from industry:**
- Linux (GPL → permissive drivers): Massive corporate contributions
- Android (Apache 2.0): Google, Samsung, others contribute heavily
- Kubernetes (Apache 2.0): 1000+ companies contribute
- TensorFlow (Apache 2.0): Thousands of external contributions

**Permissive licenses attract MORE contributions, not fewer.**

---

## 📋 Transition Process

### Phase 1: Legal & Preparation (Month 1)

**Week 1: Legal Review**
- [ ] Finalize Contributor License Agreement (CLA)
- [ ] Document all existing contributors
- [ ] Review patent implications
- [ ] Trademark protection strategy

**Week 2: Contributor Outreach**
- [ ] Contact all existing contributors
- [ ] Obtain retroactive CLA signatures
- [ ] Address contributor concerns
- [ ] Document consent process

**Week 3: Documentation**
- [ ] Update this LICENSE-TRANSITION.md
- [ ] Create transition FAQ
- [ ] Prepare public announcement
- [ ] Update contribution guidelines

**Week 4: Final Preparation**
- [ ] Test CLA automation
- [ ] Prepare repository updates
- [ ] Schedule transition date
- [ ] Brief leadership team

### Phase 2: Execution (Month 2)

**Week 1: Repository Updates**
- [ ] Update LICENSE files in all repos
- [ ] Add SPDX license identifiers to source files
- [ ] Update README badges
- [ ] Update package metadata (PyPI, npm)

**Week 2: Documentation Updates**
- [ ] Update all documentation references
- [ ] Update contribution guides
- [ ] Update legal documentation
- [ ] Update FAQ

**Week 3: Public Announcement**
- [ ] Blog post explaining rationale
- [ ] Social media announcement
- [ ] Email to contributor list
- [ ] Post to relevant forums

**Week 4: Community Support**
- [ ] Host Q&A session
- [ ] Monitor community feedback
- [ ] Address concerns individually
- [ ] Celebrate completion

### Phase 3: Resubmission & Partnerships (Month 3)

**Week 1: 3D Slicer Resubmission**
- [ ] Update SlicerOpenLIFU to Apache 2.0
- [ ] Submit extension for review
- [ ] Engage with Slicer community
- [ ] Address any technical feedback

**Week 2-4: Academic Partnerships**
- [ ] Contact Stanford, Johns Hopkins, MIT
- [ ] Present permissive licensing advantage
- [ ] Negotiate research partnerships
- [ ] Sign first agreements

---

## 📊 Impact Analysis

### Positive Impacts (Expected)

1. **3D Slicer Integration**
   - Access to 1000+ institutions
   - Community validation
   - Broader user base
   - Technical collaboration

2. **Academic Partnerships**
   - Research licensing revenue: $25K-$50K per institution
   - Target: 3-5 partnerships in Q1-Q2 2026
   - Co-publication opportunities
   - Student contributors

3. **Commercial Ecosystem**
   - OEM licensing opportunities
   - Device manufacturer partnerships
   - Cloud service integration
   - SaaS business model enabled

4. **Community Growth**
   - Reduced legal friction
   - More contributor-friendly
   - Compatible with existing projects
   - Career-safe participation

5. **Regulatory Benefits**
   - Easier FDA submissions
   - CE marking path clearer
   - Clinical trial support
   - Hospital procurement simplified

### Potential Challenges (Mitigation Plans)

1. **Community Confusion**
   - **Challenge:** Contributors don't understand change
   - **Mitigation:** Clear communication, FAQ, Q&A sessions
   - **Timeline:** Week 3 of Phase 2

2. **Ideological Concerns**
   - **Challenge:** Some prefer copyleft
   - **Mitigation:** Explain clinical translation requirements
   - **Evidence:** 3D Slicer rejection as concrete example
   - **Option:** Maintain separate AGPL fork (not recommended)

3. **Contributor Resistance**
   - **Challenge:** Some refuse CLA signature
   - **Mitigation:** Individual conversations, grandfather old contributions
   - **Fallback:** Rewrite resistant code sections

4. **Fork Risk**
   - **Challenge:** AGPL fork by copyleft advocates
   - **Mitigation:** First-mover advantage, network effects, community focus
   - **Reality:** Medical device market requires permissive

---

## 🤝 Contributor License Agreement (CLA)

### Why We Need a CLA

**Purpose:**
- Enables license transition now and future updates
- Protects contributors with patent grants
- Ensures we have rights to distribute
- Standard practice for open-source projects

**What It Does:**
- You grant license to use your contributions
- You retain copyright to your work
- You receive patent protection
- Project can relicense if needed (with TSC approval)

**What It Doesn't Do:**
- Transfer copyright to Openwater
- Limit your use of your contributions
- Give Openwater exclusive rights
- Force you to contribute

### CLA Implementation

**Automated via CLA Assistant:**
- First-time contributors sign via GitHub
- Electronic signature (legally binding)
- Stored securely
- Transparent process

**Existing Contributors:**
- Retroactive CLA required
- Email outreach with DocuSign
- Personal follow-up for major contributors
- Grandfathering for unreachable contributors

---

## 📚 Additional Resources

### For Contributors
- [CLA FAQ](https://github.com/OpenwaterHealth/openwater-commons/wiki/CLA-FAQ) (Coming Soon)
- [License Transition FAQ](https://github.com/OpenwaterHealth/openwater-commons/wiki/License-FAQ) (Coming Soon)
- [Discussion Forum](https://github.com/OpenwaterHealth/openwater-commons/discussions) (Coming Soon)

### Legal Documentation
- [Apache 2.0 License Text](https://www.apache.org/licenses/LICENSE-2.0)
- [CERN-OHL-P License Text](https://ohwr.org/cern_ohl_p_v2.txt)
- [CLA Template](https://github.com/OpenwaterHealth/openwater-commons/blob/main/docs/governance/CLA.md) (Coming Soon)

### Industry Examples
- [Linux Foundation CLA](https://www.linuxfoundation.org/legal/dco)
- [Apache Software Foundation CLA](https://www.apache.org/licenses/contributor-agreements.html)
- [Eclipse Foundation CLA](https://www.eclipse.org/legal/ECA.php)

---

## 💬 Questions & Feedback

**Have questions about the license transition?**

1. **General questions:** Open an issue with label `license-transition`
2. **Legal concerns:** Email legal@openwater.health
3. **Contributor-specific:** Email your questions to community@openwater.health
4. **Community discussion:** Join our monthly community call

**We're committed to transparency and will update this document as questions arise.**

---

## ✅ Transition Status

### Current Phase: Planning (Phase 1)
- [x] Rationale documented
- [x] Impact analysis complete
- [ ] Legal review in progress
- [ ] CLA finalization pending
- [ ] Board approval pending (presentation scheduled)

### Timeline
- **Phase 1 Completion:** End of Month 1 (2026 Q1)
- **Phase 2 Execution:** Month 2 (2026 Q1)
- **Phase 3 Partnerships:** Month 3 (2026 Q1)
- **Full Completion:** March 2026

**Next Update:** After board presentation to Vitalik Buterin

---

**This transition enables our mission: Making advanced medical technology accessible to everyone, everywhere.** 🌍

_Questions? Open an issue or join our community discussion._
