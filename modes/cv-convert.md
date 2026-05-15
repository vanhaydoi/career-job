# Mode: convert — CV Format Converter

Convert a CV from any format (PDF, DOCX, image, text, LinkedIn) into `cv.md` markdown format compatible with the career-ops system.

## Input Sources

| Source | Detection | Extraction Method |
|--------|-----------|-------------------|
| `.pdf` file | File extension | Read tool (native PDF support) |
| `.docx` file | File extension | Read tool or `minimax-docx` skill |
| `.png`, `.jpg`, `.jpeg` file | File extension | `vision-analysis` skill (OCR + structure) |
| `.txt` file | File extension | Read directly |
| LinkedIn URL | URL contains `linkedin.com` | WebFetch |
| HTML URL | URL | WebFetch |

## Workflow

### Step 0 — Detect input type

Examine `$ARGUMENTS`:
- If it's a **file path** (starts with `cv-input/` or absolute path), extract by extension
- If it's a **URL**, extract by domain
- If neither, ask the user to provide a file path or URL

### Step 1 — Extract raw text

**PDF files:**
Use the Read tool to extract text content from the PDF.

**DOCX files:**
Use the Read tool. If text extraction is incomplete, use `minimax-docx` skill.

**Image files (screenshot/photo of CV):**
Use `vision-analysis` skill:
```
Analyze this CV image. Extract ALL text content. Identify the structure: header (name, contact info), summary, work experience (company, role, dates, bullet points), education, skills, projects, certifications, languages. Return the raw text organized by section.
```

**LinkedIn URL:**
WebFetch the profile URL. Extract: name, headline, about section, experience entries (title, company, dates, description), education, skills, certifications.

**Text files:**
Read directly.

### Step 2 — Detect language

Analyze the extracted text:
- **Vietnamese (VI):** Contains Vietnamese diacritics (ắ, ể, ố, ờ, ạ, ệ, ị, ọ, ụ, ơ, ư)
- **English (EN):** Default
- **Bilingual:** If both present, detect the dominant language. Note: common for Vietnamese CVs to have both VI and EN content.

If Vietnamese is detected, note whether the CV follows Vietnamese conventions:
- Personal info section (DOB, gender, marital status, photo)
- Education before experience
- References section
- These may differ from the career-ops `cv.md` schema

### Step 3 — Structure into cv.md format

Map extracted content to the standard `cv.md` schema:

```markdown
# CV -- {Full Name}

**Location:** {city, country}
**Email:** {email}
**LinkedIn:** {linkedin_url}
**Portfolio:** {portfolio_url}
**GitHub:** {github_url}

## Professional Summary
{3-5 sentences. If source has no summary, draft one from experience. Include top achievement metrics.}

## Work Experience

### {Company} -- {Location}
**{Role}**
{start_date}-{end_date}

- {bullet point with metric if possible}
- ...

## Projects
- **{Project Name}** ({type}) -- {description}. {metric if available}

## Education
- {Degree}, {School} ({year})

## Certifications
- {Certification}, {Issuer} ({year})

## Skills
- **{Category}:** {skills list}
```

### Step 4 — Handle Vietnamese CV specifics

If the CV is Vietnamese:

1. **Strip personal info** not relevant to international applications: DOB, gender, marital status, photo references. Note to user what was removed.
2. **Reorder sections** to career-ops standard: Summary → Experience → Projects → Education → Skills (education moves down)
3. **Translate company/role context** if needed — keep original Vietnamese names but add English context in parentheses for mixed-language CVs
4. **Preserve bilingual content** — if the original is bilingual, generate the markdown in English with Vietnamese terms where appropriate

### Step 5 — Flag issues

After structuring, flag any concerns:

| Issue | Severity | Action |
|-------|----------|--------|
| Missing dates on experience | Medium | Note, user can add later |
| No metrics/numbers in bullets | Low | Suggest where metrics could go |
| Section missing entirely | Medium | Flag, user may need to provide |
| Ambiguous company/role names | Low | Note, user to verify |
| Non-standard sections found | Low | Preserve as-is under an "Other" section |

### Step 6 — Write output

1. Write the structured CV to `cv-input/converted/{filename}.md`
2. Show the user a diff/summary of what was extracted and structured
3. **NEVER overwrite `cv.md`** — the user must manually copy the converted file to root
4. **NOTE:** Converted CVs in `cv-input/converted/` are auto-detected by `new-cv` wizard. If the user later runs `/career-ops new-cv`, the wizard will offer to pre-fill answers from these files.

### Step 7 — Report

```
CV Conversion Complete
━━━━━━━━━━━━━━━━━━━━━━━━
Source: {file path or URL}
Format: {pdf|docx|image|text|linkedin}
Language: {VI|EN|bilingual}
Output: cv-input/converted/{filename}.md

Sections found: {list}
Sections missing: {list}

Issues flagged: {N}

→ Review cv-input/converted/{filename}.md
→ Copy to cv.md when ready: cp cv-input/converted/{filename}.md cv.md
```
