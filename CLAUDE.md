# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a French automated blog project using Hugo static site generator. It's designed to generate automated news content and deploy to Netlify. The blog uses the PaperMod theme and includes the Anthropic AI SDK for content generation.

## Essential Commands

### Hugo Commands
- `hugo server -D` - Start development server with drafts
- `hugo --minify` - Build for production (used by Netlify)
- `hugo new posts/article-name.md` - Create new blog post

### Deployment
- Deploys automatically to Netlify on git push
- Production URL: https://monblogauto.netlify.app
- Build command: `hugo --minify`
- Publish directory: `public`

## Project Structure

### Content Management
- `content/posts/` - Blog articles in Markdown format
- `archetypes/default.md` - Template for new posts
- `hugo.yaml` - Main Hugo configuration (French locale, site metadata)
- `netlify.toml` - Netlify deployment configuration

### Theme and Layout
- Uses PaperMod theme in `themes/PaperMod/`
- Custom layouts in `layouts/` override theme defaults
- `layouts/index.html` - Custom homepage showing latest articles
- `layouts/_default/baseof.html` and `layouts/_default/single.html` - Custom page templates

### AI Integration
- `@anthropic-ai/sdk` dependency for content generation
- Package is CommonJS type
- No custom build scripts currently defined

## Content Guidelines

### Blog Post Format
Posts use Hugo front matter with:
- `title` - Article title
- `date` - Publication date (format: 2025-07-24T10:00:00+02:00)
- `draft: false` - Set to false for published posts
- `tags` - Array of tags for categorization

### Site Configuration
- Site language: French (`fr-fr`)
- Base URL configured for Netlify deployment
- Menu includes Home and Archives sections
- Social icons configured (GitHub placeholder)

## Development Notes

- Hugo version 0.148.1 specified in Netlify config
- No test suite currently configured
- Uses Git for version control with automated Netlify deployment
- Static assets served from `static/` directory
- Generated site outputs to `public/` directory