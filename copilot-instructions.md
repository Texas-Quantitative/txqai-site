# Copilot Instructions for TXQ AI Site

## 🚨 CRITICAL: Read Development Best Practices FIRST

**MANDATORY FOR ALL AGENTS**: Before making ANY changes to this project, review the TQFA Development Best Practices.

**📚 Best Practices Document**: 
`https://github.com/Texas-Quantitative/tqfa-development-best-practices/blob/main/TQFA_DEVELOPMENT_BEST_PRACTICES.md`

**Key Topics Covered:**
- Deployment Workflow & Version Management
- Architecture Decision Protocol
- Security Best Practices (authentication, encryption)
- Common Pitfalls & Solutions
- Agent Handoff Protocol

**Tools Available**: Use `fetch_webpage` or `github_repo` tools to access this content when needed.

**Core Principles to Follow:**
1. ✅ **Version Everything** - Bump versions before deploying
2. ✅ **Test Locally First** - Dev branch before UAT
3. ✅ **Extend, Don't Duplicate** - Avoid creating similar methods
4. ✅ **Ask Before Major Changes** - Architectural decisions need consultation

## Project-Specific Guidelines

**Architecture**: Zero-build static site (HTML + Tailwind via CDN)
- No npm/build tools due to previous complications
- Pure HTML/CSS with minimal inline JavaScript
- Tailwind CDN for styling

**Color Palette** (maintain consistency):
- tq.ink: #0b1220 (dark navy)
- tq.sky: #0ea5e9 (primary blue)
- tq.mint: #34d399 (accent green)
- tq.steel: #1f2937 (dark gray)
- tq.sand: #f3f4f6 (light gray)

**File Structure**:
- index.html (homepage)
- work.html (portfolio/case studies)
- approach.html (methodology)
- about.html (company info)
- contact.html (contact form)
- privacy.html (privacy policy)

**Key Requirements**:
- Consistent header/footer across all pages
- Active navigation state indication
- Professional typography and spacing
- Responsive design using Tailwind classes
- GitHub Pages hosting compatibility