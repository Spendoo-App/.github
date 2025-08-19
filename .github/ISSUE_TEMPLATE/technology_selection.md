name: "Technology Selection"
description: "Evaluate and decide on a technology choice (e.g. reverse proxy, database, framework)"
about: "Intended Use - New TS tickets" 
title: "Tech Decision: <short description>"
labels: ["tech-decision", "discussion"]
body:
  - type: markdown
    attributes:
      value: |
        ## 🎯 Context / Problem
        *Why do we need this decision? What problem are we trying to solve?*
  - type: textarea
    id: context
    attributes:
      label: Context
      description: Briefly describe why this decision is needed.
      placeholder: We need a reverse proxy to handle routing, TLS termination, load balancing...
    validations:
      required: true

  - type: markdown
    attributes:
      value: |
        ## ✅ Requirements
        *List concrete must-haves for this decision.*
  - type: textarea
    id: requirements
    attributes:
      label: Requirements
      description: What are the key requirements this choice must satisfy?
      placeholder: e.g. Supports automatic TLS, works in Kubernetes, handles WebSockets...
    validations:
      required: true

  - type: markdown
    attributes:
      value: |
        ## 🔗 Dependencies
        *What other decisions does this depend on, and what will depend on this one?*
  - type: textarea
    id: dependencies
    attributes:
      label: Dependencies
      description: Capture prerequisites and downstream impacts.
      placeholder: |
        **Prerequisite decisions:**  
        - Hosting platform (VMs, Docker, Kubernetes)  
        - TLS management strategy  

        **Downstream decisions:**  
        - Monitoring stack  
        - CI/CD automation  
    validations:
      required: false

  - type: markdown
    attributes:
      value: |
        ## 🤔 Options to Consider
        *What are the candidate technologies?*
  - type: textarea
    id: options
    attributes:
      label: Options
      description: List the possible technologies.
      placeholder: |
        - NGINX — battle-tested, flexible  
        - Traefik — Docker/K8s integration, auto TLS  
        - Caddy — simple config, auto HTTPS  
        - HAProxy — top performance
    validations:
      required: true

  - type: markdown
    attributes:
      value: |
        ## 🔍 Evaluation Criteria
        *How will we compare the options?*
  - type: textarea
    id: criteria
    attributes:
      label: Evaluation Criteria
      description: Define how you’ll assess the options.
      placeholder: e.g. Ease of config, performance, ecosystem, maintainability...
    validations:
      required: true

  - type: markdown
    attributes:
      value: |
        ## 📊 Comparison (optional)
        *Table or notes comparing each option against the criteria.*
  - type: textarea
    id: comparison
    attributes:
      label: Comparison
      description: Structured comparison of the options.
      placeholder: |
        | Option  | Ease of Use | Performance | TLS Support | Notes |
        |---------|-------------|-------------|-------------|-------|
        | NGINX   | Medium      | High        | Manual      | Config heavy |
        | Traefik | Easy        | Medium      | Built-in    | Best with K8s |
    validations:
      required: false

  - type: markdown
    attributes:
      value: |
        ## 💬 Discussion
        *Capture key trade-offs, team preferences, open questions.*
  - type: textarea
    id: discussion
    attributes:
      label: Discussion
      description: Points to debate and questions for the team.
      placeholder: Do we prioritize simplicity over fine-grained control?
    validations:
      required: false

  - type: markdown
    attributes:
      value: |
        ## ⚠️ Technical Debt Considerations
        *What risks or trade-offs does this decision introduce?*
  - type: textarea
    id: technical-debt
    attributes:
      label: Technical Debt
      description: Risks of lock-in, migration cost, skill gaps, scaling ceilings, etc.
      placeholder: |
        - Migration from Caddy to NGINX later may require major config rewrites  
        - HAProxy requires more specialized ops knowledge  
        - Traefik smaller community → fewer long-term resources  
    validations:
      required: false

  - type: markdown
    attributes:
      value: |
        ## 📌 Next Steps
        *How will we reach a final decision?*
  - type: textarea
    id: next-steps
    attributes:
      label: Next Steps
      description: Define the plan forward (feedback, POCs, timeline).
      placeholder: |
        - Gather team input by <date>  
        - Run proof-of-concept with top 2 candidates  
        - Document final decision in architecture repo
    validations:
      required: true
