---
name: aiml-research-curator
description: Curate AI/ML research papers and articles from whitelisted academic sources (arXiv, ACM, IEEE), technical blogs (Google AI, OpenAI, Meta AI, Anthropic, Hugging Face), and newsletters, supplemented with community insights from Reddit and social media. Use this skill when the user requests research on AI/ML topics, literature reviews, paper summaries, or wants a curated list of academic sources with citations. Outputs a structured markdown document with summaries and proper citations grounded in whitelisted sources.
---

# AI/ML Research Curator

## Overview

This skill enables comprehensive curation of AI/ML research papers and articles from trusted academic and industry sources. It produces structured markdown documents with summaries and proper citations, ensuring all content is grounded in whitelisted sources.

## Core Workflow

### Step 1: Read Whitelisted Sources

**ALWAYS start by reading the whitelisted sources reference**:

```bash
view /mnt/skills/user/aiml-research-curator/references/whitelisted_sources.md
```

This document contains:
- Complete list of trusted academic, technical, and community sources
- Search strategies for each source type
- Citation requirements and formats

### Step 2: Conduct Research

Research follows a two-phase approach:

#### Phase 1: Academic & Technical Sources (Primary)

Search whitelisted sources in priority order:

1. **Academic papers** - Start with arXiv, Papers With Code, OpenReview
   - Use: `web_search("site:arxiv.org [topic]")`
   - Fetch full papers: `web_fetch([arxiv_url])`
   
2. **Company research blogs** - Google AI, OpenAI, Meta AI, Anthropic, DeepMind, Microsoft Research, Hugging Face
   - Use: `web_search("site:ai.googleblog.com [topic]")`
   - Use: `web_search("site:openai.com/research [topic]")`
   
3. **Technical publications** - The Batch, The Gradient, Towards Data Science
   - Use: `web_search("site:thegradient.pub [topic]")`

**Key principle**: Only use content from whitelisted domains. If a search returns non-whitelisted sources, continue searching until whitelisted sources are found.

#### Phase 2: Community Insights (Supplementary)

Add practical context from community sources:

1. **Reddit discussions**
   - Use: `web_search("site:reddit.com/r/MachineLearning [topic]")`
   - Use: `web_search("site:reddit.com/r/LocalLLaMA [topic]")`

2. **Hacker News**
   - Use: `web_search("site:news.ycombinator.com [topic]")`

3. **Implementation repositories**
   - Check Papers With Code for code links
   - Verify GitHub repositories are linked from whitelisted sources

**Important**: Community sources provide context only. Primary claims must come from Phase 1 sources.

### Step 3: Structure the Output

Use the output template as a guide (view it if needed):

```bash
view /mnt/skills/user/aiml-research-curator/assets/output_template.md
```

Create a markdown document with these sections:

1. **Executive Summary** - High-level overview of findings (2-3 paragraphs)

2. **Key Papers & Publications** - Academic papers with:
   - Full citation (authors, title, venue, date)
   - Direct URL
   - 2-3 paragraph summary
   - Key contributions (bullet points)
   - Relevance to the query

3. **Technical Blog Posts & Company Research** - Industry research with:
   - Source attribution (Google AI Blog, OpenAI, etc.)
   - Publication date and URL
   - Summary of content
   - Key takeaways

4. **Community Insights & Practical Context** - Reddit, Hacker News, implementations:
   - Links to discussions
   - Summary of practical challenges/applications
   - Available code implementations

5. **Emerging Trends & Future Directions** - Synthesis across sources

6. **Recommended Reading Order** - Guided path for different audiences

7. **References** - Complete numbered list with URLs

### Step 4: Ensure Proper Citations

**Critical requirement**: Every claim must be grounded in whitelisted sources with citations.

Citation format:
- Inline: `[Source, Year]` or `[Author et al., Year]`
- Example: "Constitutional AI approaches [Anthropic, 2023] focus on..."
- Include direct URLs in References section

**Verification checklist**:
- ✓ All papers cited are from whitelisted sources
- ✓ All blog posts are from whitelisted company blogs
- ✓ Community insights clearly marked as supplementary
- ✓ Direct URLs provided for all sources
- ✓ No claims without attribution

### Step 5: Output the Document

Save the curated research to `/mnt/user-data/outputs/` with a descriptive filename:

```bash
# Example
/mnt/user-data/outputs/aiml_research_transformers_2024.md
```

Use the present_files tool to share with the user.

## Search Strategy Guidelines

### For Broad Topics (e.g., "transformers", "reinforcement learning")
1. Search arXiv for recent papers (5-10 results)
2. Check 2-3 company blogs for technical posts
3. Search Papers With Code for implementations
4. Add Reddit/HN context for practical insights

### For Specific Techniques (e.g., "RLHF", "LoRA fine-tuning")
1. Search arXiv with specific term
2. Check relevant company blog (e.g., Anthropic for RLHF)
3. Search Hugging Face blog for implementation guides
4. Check Reddit for community experiences

### For Recent Developments (e.g., "latest LLM research")
1. Search company blogs first (most recent announcements)
2. Search arXiv with date filters
3. Check The Batch newsletter
4. Reddit/HN for community reaction

### For Implementation-Focused Research
1. Start with Papers With Code
2. Check Hugging Face blog
3. Search Towards Data Science for tutorials
4. Reddit for real-world deployment experiences

## Quality Standards

### Summaries
- Write in your own words (no copy-paste from sources)
- Focus on key contributions and methodology
- Explain relevance to the research query
- Keep technical but accessible

### Citations
- Never make claims without source attribution
- Prefer primary sources (papers) over secondary (blog summaries)
- Cross-reference claims across multiple sources when possible
- Include publication dates for temporal context

### Organization
- Logical flow from foundational to advanced
- Group related papers together
- Separate academic work from industry research
- Clearly distinguish community insights from authoritative sources

## Common Patterns

### Literature Review Pattern
User asks: "What are the latest developments in [topic]?"

1. Search arXiv for recent papers (last 6-12 months)
2. Check company blogs for major announcements
3. Identify common themes and trends
4. Organize chronologically or thematically
5. Highlight most impactful contributions

### Implementation Guide Pattern
User asks: "How do I implement [technique]?"

1. Find the original paper on arXiv
2. Search Papers With Code for implementations
3. Check Hugging Face blog for tutorials
4. Add Reddit discussions on practical challenges
5. Structure as: Theory → Implementation → Best Practices

### Comparative Analysis Pattern
User asks: "Compare [approach A] vs [approach B]"

1. Find foundational papers for both approaches
2. Search for comparison papers or blog posts
3. Look for benchmark results on Papers With Code
4. Add community discussions on practical differences
5. Structure as: Overview → Approach A → Approach B → Comparison

## Troubleshooting

**Issue**: No whitelisted sources found for topic
- **Solution**: Broaden search terms, try related keywords, check if topic is too new/niche

**Issue**: Too many results to process
- **Solution**: Add constraints (date range, specific subtopic), focus on highest-impact sources

**Issue**: Community sources contradict academic sources
- **Solution**: Prioritize academic sources, note discrepancies, investigate further if significant

**Issue**: Unclear citation requirements
- **Solution**: Always cite. When in doubt, over-cite rather than under-cite.

## Resources

This skill includes:

### references/whitelisted_sources.md
Complete list of trusted AI/ML sources with search strategies and citation requirements. **Read this first** before conducting any research.

### assets/output_template.md
Markdown template showing the expected structure and format for curated research outputs. Use as a guide for organizing your findings.
