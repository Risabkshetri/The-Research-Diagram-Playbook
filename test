flowchart TD
    subgraph INPUT["USER INPUT"]
        A["topic + tone + type + keywords + [raw_content] + [notes]"]
    end

    subgraph PHASE1["PHASE 1: ANALYZE"]
        B1["Quantitative\n(sentence len,\nreading grade,\nformatting)"]
        B2["LLM Qualitative\n(voice, tone,\nhook style,\npatterns)"]
        B1 --> B3
        B2 --> B3
        B3["WritingProfile"]
    end

    subgraph PHASE2["PHASE 2: RESEARCH"]
        C1["Keyword\nDiscovery\n(SearchTool)"] --> C2["SERP\nAnalysis\n(BrowserTool)"]
        C2 --> C3["Fact\nGathering\n(SearchTool)"]
        C3 --> C4["Question\nDiscovery\n(LLM)"]
        C4 --> C5["ResearchResult"]
    end

    subgraph PHASE3["PHASE 3: PLAN"]
        D1["WritingProfile + ResearchResult → LLM → BlogOutline\n(H1 + H2s + H3s + hook strategy + FAQ questions + meta tags)"]
    end

    subgraph PHASE4["PHASE 4: WRITE"]
        E1["For each section:\nBlogOutline.section[i] + WritingProfile + facts → LLM → text"]
        E2["Hook → Intro → Body sections → FAQ → Conclusion → CTA"]
        E1 --> E2
        E2 --> E3["Raw Blog Draft (Markdown)"]
    end

    subgraph PHASE5["PHASE 5: REFINE"]
        F1["SEO Audit\n(Python)"] --> F2["Readability\nScore\n(Python)"]
        F2 --> F3["LLM Polish\n(fix issues)"]
        F3 --> F4["Final Blog Post (Markdown)\n+ SEO Audit Report (JSON)\n+ Outline (JSON)\n+ Research Data (JSON)"]
    end

    subgraph PHASE6["PHASE 6: PUBLISH"]
        G1["Build Zobique\nFrontmatter\n(author, cat,\nmeta, tags)"] --> G2["Write .md to\ncontent/ dir\n(blog-frontend)"]
        G2 --> G3["Run blog\nplatform CLI\n(npm run\nblog:upload)"]
        G3 --> G4["Supabase articles table (draft/published)\nLive at: blog.zobique.com/blog/{slug}"]
    end

    INPUT --> PHASE1
    PHASE1 --> PHASE2
    PHASE2 --> PHASE3
    PHASE3 --> PHASE4
    PHASE4 --> PHASE5
    PHASE5 --> PHASE6
