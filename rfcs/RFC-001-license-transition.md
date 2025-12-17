# RFC-001: License Transition to Apache 2.0 / CERN-OHL-P

**Status:** TSC Review  
**Author:** Daniel Blizinski (Director of Open-Source Business Strategy)  
**Created:** December 2025  
**Last Updated:** December 2025

---

## Summary

Transition Openwater's licensing from AGPL-3.0 to Apache 2.0 (for software/firmware) and CERN-OHL-P (for hardware designs) to enable clinical translation, academic partnerships, and integration with the medical imaging ecosystem.

---

## Motivation

### Problem Statement

Our current AGPL-3.0 licensing creates barriers to:
1. **Clinical deployment** - Hospitals cannot use AGPL software due to source disclosure requirements
2. **Academic research** - Universities avoid AGPL dependencies in grant-funded research
3. **Ecosystem integration** - Medical imaging community (3D Slicer, MONAI, etc.) uses permissive licenses
4. **Commercial partnerships** - Device manufacturers cannot integrate AGPL components

**Critical Evidence:** SlicerOpenLIFU was rejected by 3D Slicer community specifically due to AGPL licensing, with feedback: "Permissive licenses are the standard in medical image computing because restrictive licenses practically prevent translating prototypes into clinical use."

### Use Cases

**Researcher at Mayo Clinic:**
- Needs to modify Openwater software for IRB-approved clinical trial
- Cannot disclose modifications due to unpublished research
- Current AGPL license blocks participation

**Medical Device OEM:**
- Wants to license Openwater ultrasound technology
- Needs to integrate with proprietary control systems
- AGPL incompatibility prevents deal

**3D Slicer User:**
- Wants to use SlicerOpenLIFU for treatment planning
- 3D Slicer community rejects AGPL extensions
- Cannot access our platform

### Impact

**Affected Parties:**
- All Openwater contributors (need to sign CLA)
- Academic partners (can now participate)
- Medical device companies (can now integrate)
- Clinical researchers (can now use in trials)
- 3D Slicer community (can now accept our extension)

---

## Design

### License Selection

**Software & Firmware:** AGPL-3.0 → **Apache 2.0**
- Industry standard for open-source medical software
- Used by: 3D Slicer (BSD), MONAI (Apache 2.0), PyTorch (BSD), ITK (Apache 2.0)
- Provides patent protection for contributors
- Enables clinical translation and commercial use

**Hardware:** AGPL-3.0 → **CERN-OHL-P** (Permissive)
- Designed specifically for open hardware
- Used by: Arduino, RISC-V Foundation
- Permissive variant allows commercial manufacturing
- Compatible with Apache 2.0 software

**Documentation:** CC-BY-4.0 (no change)
- Already permissive
- Standard for documentation

### Repository Mapping

**Apache 2.0 (Software/Firmware):**
- OpenLIFU-python
- SlicerOpenLIFU
- OpenLIFU-3DScanner
- All firmware repositories
- OpenMOTION-Pylib
- All OpenMOTION software

**CERN-OHL-P (Hardware):**
- OpenLIFU-hardware-mechanical
- OpenLIFU-hardware-electrical
- OpenMOTION-hardware-mechanical
- OpenMOTION-hardware-electrical
- All BOM repositories

---

## Alternatives Considered

### Alternative 1: Keep AGPL-3.0
**Pros:** Strong copyleft protection  
**Cons:** Blocks clinical use, academic partnerships, ecosystem integration  
**Why not chosen:** 3D Slicer rejection proves this blocks our mission

### Alternative 2: GPL-3.0
**Pros:** Less restrictive than AGPL  
**Cons:** Still blocks clinical use and OEM partnerships  
**Why not chosen:** Medical device ecosystem requires permissive

### Alternative 3: Dual Licensing (AGPL + Commercial)
**Pros:** Offers permissive path via commercial license  
**Cons:** Complex, creates friction, not standard in medical OSS  
**Why not chosen:** Community prefers single permissive license

### Alternative 4: MIT or BSD
**Pros:** Even more permissive  
**Cons:** No patent protection for contributors  
**Why not chosen:** Apache 2.0 provides better contributor protection

---

## Implementation Plan

### Phase 1: Legal & Preparation (Month 1)
- [ ] Finalize Contributor License Agreement (CLA)
- [ ] Document all existing contributors
- [ ] Obtain retroactive CLA signatures
- [ ] Legal review and board approval

### Phase 2: Execution (Month 2)
- [ ] Update LICENSE files in all repositories
- [ ] Add SPDX license identifiers to source files
- [ ] Update README badges and package metadata
- [ ] Public announcement and FAQ

### Phase 3: Resubmission & Partnerships (Month 3)
- [ ] Resubmit SlicerOpenLIFU to 3D Slicer community
- [ ] Contact academic partners (Stanford, Johns Hopkins, MIT)
- [ ] Begin commercial partnership discussions

### Timeline
**Start:** January 2026  
**Completion:** March 2026

---

## Impact Analysis

### Breaking Changes
**None** - License change doesn't affect code functionality

### Migration Path
Users simply receive software under new license. No code changes required.

### Backwards Compatibility
Fully maintained. Apache 2.0 allows same uses as AGPL plus more.

### Dependencies
**Required:**
- Board approval (Vitalik Buterin presentation)
- Legal review complete
- CLA signatures from existing contributors

---

## Testing Plan

### Validation
- [ ] Legal review confirms licensing is correct
- [ ] All files have proper SPDX identifiers
- [ ] Package metadata updated (PyPI, npm)
- [ ] 3D Slicer accepts SlicerOpenLIFU

---

## Documentation

### Documentation Updates
- [ ] LICENSE-TRANSITION.md (rationale)
- [ ] CLA documentation
- [ ] FAQ for contributors
- [ ] Contributing guide updated

### Communication Plan
- [ ] Board presentation (evidence: 3D Slicer rejection)
- [ ] Blog post announcing transition
- [ ] Email to contributor list
- [ ] Social media announcement
- [ ] Forum post with Q&A

---

## Open Questions

- [x] Will board approve? (Presentation scheduled)
- [ ] Timeline for CLA signatures?
- [ ] Any contributors unable to sign CLA?

---

## References

- [LICENSE-TRANSITION.md](../LICENSE-TRANSITION.md) - Full rationale
- [3D Slicer Licensing Policy](https://www.slicer.org/wiki/License)
- [Apache 2.0 License](https://www.apache.org/licenses/LICENSE-2.0)
- [CERN-OHL-P](https://ohwr.org/cern_ohl_p_v2.txt)

---

## Discussion

[GitHub Discussion Thread](https://github.com/OpenwaterHealth/openwater-commons/discussions) - TBD

---

## Decision

**TSC Vote:** Pending  
**Outcome:** Pending TSC review  
**Board Approval:** Presentation scheduled with Vitalik Buterin

**Next Steps:**
1. TSC review and vote
2. Board presentation and approval
3. Begin implementation Phase 1
