# DevOS Architecture

## Overview

DevOS is organized as a documentation-led framework for developer workspaces. It separates policy, execution, profiles, projects, and documentation so each part can evolve without collapsing into a single opaque system.

## Layer Model

### 1. Core

**Purpose**
- Hold canonical rules, standards, and framework identity.

**Responsibility**
- Define policy, standards, and architecture decisions.
- Provide stable reference material for all other layers.

**Example Contents**
- Policies
- Standards
- Manifesto
- ADRs

**Relations**
- Guides every other layer.
- Must remain stable and explicit.

### 2. Engine

**Purpose**
- Provide the operational logic that applies rules in practice.

**Responsibility**
- Coordinate workspace behaviors.
- Enforce safe workflow patterns.
- Translate policy into repeatable operations.

**Example Contents**
- Validation logic
- Safe setup routines
- Workspace checks

**Relations**
- Consumes Core.
- Serves Profiles, Projects, and Integrations.

### 3. Integration

**Purpose**
- Connect DevOS to external tools and agents.

**Responsibility**
- Normalize interactions with AI coding agents and developer tools.
- Keep external tool behavior behind explicit boundaries.

**Example Contents**
- Agent prompt adapters
- Tool-specific conventions
- Compatibility notes

**Relations**
- Depends on Core guidance.
- Used by Profiles and Projects.

### 4. Profiles

**Purpose**
- Describe workstation variants and user-specific setups.

**Responsibility**
- Capture environment preferences.
- Define workspace defaults.

**Example Contents**
- Default profile
- Tool preferences
- User workspace settings

**Relations**
- Built on Core and Engine.
- Applied before Projects.

### 5. Projects

**Purpose**
- Hold actual developer work products.

**Responsibility**
- Contain source code, tests, and project-specific documentation.
- Stay separate from framework rules.

**Example Contents**
- Application source code
- Tests
- Build metadata

**Relations**
- Follow Core standards.
- May use Integration and Profiles.

### 6. Documentation

**Purpose**
- Record how DevOS works and how to use it.

**Responsibility**
- Explain architecture, workflow, and decisions.
- Keep onboarding and maintenance predictable.

**Example Contents**
- Getting started guide
- FAQ
- ADRs
- Workflow docs

**Relations**
- Documents every other layer.
- Must reflect reality, not intention.

## Design Rules

- Core defines.
- Engine applies.
- Integration connects.
- Profiles specialize.
- Projects use.
- Documentation explains.

## Maintenance Principle

If a change affects behavior, update documentation in the same change set.
