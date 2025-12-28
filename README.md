# AI/ML Research Curator Skill

A comprehensive Claude skill for curating AI/ML research papers and articles from trusted academic and industry sources. This skill enables systematic research curation with proper citations, structured outputs, and quality control through whitelisted sources.

## Overview

The AI/ML Research Curator transforms Claude into a specialized research assistant that:
- **Searches only whitelisted sources** (arXiv, ACM, IEEE, company research blogs)
- **Supplements with community insights** from Reddit, Hacker News, and GitHub
- **Produces structured markdown reports** with proper citations
- **Ensures all claims are grounded** in authoritative sources

## Features

### Whitelisted Academic Sources
- **Preprint Servers**: arXiv, Papers With Code, OpenReview
- **Publishers**: ACM Digital Library, IEEE Xplore, JMLR
- **Research Blogs**: Google AI, OpenAI, Meta AI, Anthropic, DeepMind, Microsoft Research, Hugging Face

### Community Sources
- Reddit communities (r/MachineLearning, r/LocalLLaMA, r/artificial)
- Hacker News discussions
- GitHub implementations via Papers With Code

### Structured Output
- Executive summary of findings
- Curated papers with detailed summaries
- Technical blog highlights
- Community insights and practical context
- Recommended reading order
- Complete bibliography with URLs

## Installation

1. Download the `aiml-research-curator.skill` file from the releases
2. In Claude, go to Settings → Skills
3. Upload the `.skill` file
4. The skill will be automatically available

## Usage Examples

### Broad Topic Research
```
Research the latest developments in transformer architectures
```

### Specific Technique
```
Find papers and resources on RLHF (Reinforcement Learning from Human Feedback)
```

### Implementation-Focused
```
I need resources on fine-tuning LLMs with LoRA - papers, tutorials, and code
```

### Literature Review
```
Curate a literature review on AI safety and alignment research from the past year
```

### Comparative Analysis
```
Compare different approaches to AI interpretability - mechanistic interpretability vs. feature visualization
```

## Output Structure

The skill generates markdown documents with:

1. **Executive Summary** - High-level overview of findings
2. **Key Papers & Publications** - Academic research with:
   - Full citations (authors, title, venue, date)
   - Direct URLs
   - 2-3 paragraph summaries
   - Key contributions
   - Relevance to query

3. **Technical Blog Posts** - Industry research with:
   - Source attribution
   - Publication dates and URLs
   - Content summaries
   - Key takeaways

4. **Community Insights** - Practical context from:
   - Reddit discussions
   - Hacker News threads
   - GitHub implementations

5. **Emerging Trends** - Synthesis and future directions
6. **Recommended Reading Order** - Guided learning paths
7. **References** - Complete bibliography with URLs

## Directory Structure

```
aiml-research-curator/
├── SKILL.md                           # Main skill instructions
├── references/
│   └── whitelisted_sources.md        # Comprehensive source list
└── assets/
    └── output_template.md             # Output format template
```

## Key Components

### SKILL.md
Contains the complete workflow instructions for Claude:
- 5-step research process
- Search strategies for different source types
- Citation requirements
- Quality standards
- Common usage patterns

### whitelisted_sources.md
Authoritative list of trusted AI/ML sources including:
- Search strategies for each source type
- URL patterns for verification
- Citation formats
- Source priorities

### output_template.md
Template showing expected structure and formatting for curated research outputs.

## Best Practices

### Be Specific
- **Good**: "Constitutional AI and RLAIF approaches"
- **Less ideal**: "AI safety"

### Specify Timeframe
```
Latest 2024 research on multimodal LLMs
```

### Indicate Use Case
- "For implementation" → More tutorials and code
- "For academic understanding" → More papers

### Request Comparison
```
Compare LoRA vs full fine-tuning for LLMs
```

## What Makes This Different

Unlike simple web searches, this skill:
- ✅ **Filters to quality sources** - Only whitelisted academic and industry sources
- ✅ **Provides context** - Combines academic rigor with practical insights
- ✅ **Ensures citations** - Every claim is grounded and cited
- ✅ **Structures information** - Organized for different use cases
- ✅ **Saves time** - Pre-configured knowledge of where to find AI/ML content

## Development

This skill was created using the skill-creator framework and follows best practices for:
- Progressive disclosure (metadata → SKILL.md → references)
- Concise instructions (Claude is already smart)
- Clear workflow structure
- Separation of concerns (instructions vs. reference data vs. templates)

## Example Output

When you use this skill, you'll receive a markdown document like:

```markdown
# AI/ML Research Curation: Transformer Architectures

**Date**: December 28, 2024
**Research Query**: Latest developments in transformer architectures
**Sources Consulted**: 15 whitelisted sources + 8 community sources

## Executive Summary
[High-level overview of transformer architecture developments...]

## Key Papers & Publications

### 1. Attention Is All You Need
**Authors**: Vaswani, A., et al.
**Published**: 2017, NeurIPS
**Source**: arXiv:1706.03762
**Link**: https://arxiv.org/abs/1706.03762

**Summary**: [Detailed summary...]
**Key Contributions**: [Bullet points...]

[Additional papers...]

## References
1. Vaswani, A., et al. (2017). "Attention Is All You Need"...
[Complete bibliography...]
```

## Contributing

This is an open-source skill. Contributions are welcome:
- Add new whitelisted sources
- Improve search strategies
- Enhance output templates
- Report issues or suggest improvements

## License

MIT License - See LICENSE file for details

## Acknowledgments

Created as part of learning Claude's skill creation framework. Special thanks to:
- Anthropic for the skill-creator documentation
- The AI/ML research community for maintaining quality open-access resources

## Links

- **GitHub Repository**: https://github.com/rakavaram5501/ai-learning-curator
- **Issues**: https://github.com/rakavaram5501/ai-learning-curator/issues
- **Latest Release**: Check releases for the `.skill` file

## Version

**Current Version**: 1.0.0  
**Last Updated**: December 28, 2024

---

**Note**: This skill requires Claude with web search capabilities enabled. It's designed to work within Claude.ai or Claude API with appropriate tool access.
