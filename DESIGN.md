---
version: alpha
name: Wikipedia iOS Design System
description: Canonical guidance for content-first Wikipedia iOS interfaces built with WMFComponents, including the four user-selectable reading appearances.
colors:
  primary: "#3366CC"
  on-primary: "#FFFFFF"
  accent: "#00AF89"
  on-surface: "#202122"
  on-surface-secondary: "#72777D"
  surface: "#FFFFFF"
  surface-subtle: "#F8F9FA"
  background: "#EAECF0"
  surface-popover: "#FFFFFF"
  chrome: "#FFFFFF"
  outline: "#A2A9B1"
  outline-subtle: "#EAECF0"
  icon: "#C8CCD1"
  icon-background: "#72777D"
  error: "#DD3333"
  warning: "#FF9500"
  success: "#14866D"
  secondary-action: "#2A4B8D"
  selection: "#EAF3FF"
  tag: "#3366CC"
  tag-background: "#3366CC1A"
  scrim: "#00000080"
typography:
  large-title: { fontFamily: SF Pro, fontSize: 34px, fontWeight: 400 }
  title-1: { fontFamily: SF Pro, fontSize: 28px, fontWeight: 400 }
  title-1-bold: { fontFamily: SF Pro, fontSize: 28px, fontWeight: 700 }
  title-2: { fontFamily: SF Pro, fontSize: 22px, fontWeight: 400 }
  title-2-bold: { fontFamily: SF Pro, fontSize: 22px, fontWeight: 700 }
  title-3: { fontFamily: SF Pro, fontSize: 20px, fontWeight: 400 }
  title-3-semibold: { fontFamily: SF Pro, fontSize: 20px, fontWeight: 600 }
  title-3-bold: { fontFamily: SF Pro, fontSize: 20px, fontWeight: 700 }
  headline: { fontFamily: SF Pro, fontSize: 17px, fontWeight: 400 }
  headline-semibold: { fontFamily: SF Pro, fontSize: 17px, fontWeight: 600 }
  headline-bold: { fontFamily: SF Pro, fontSize: 17px, fontWeight: 700 }
  body: { fontFamily: SF Pro, fontSize: 17px, fontWeight: 400 }
  body-bold: { fontFamily: SF Pro, fontSize: 17px, fontWeight: 700 }
  callout: { fontFamily: SF Pro, fontSize: 16px, fontWeight: 400 }
  subheadline: { fontFamily: SF Pro, fontSize: 15px, fontWeight: 400 }
  subheadline-medium: { fontFamily: SF Pro, fontSize: 15px, fontWeight: 500 }
  subheadline-semibold: { fontFamily: SF Pro, fontSize: 15px, fontWeight: 600 }
  footnote: { fontFamily: SF Pro, fontSize: 13px, fontWeight: 400 }
  caption-1: { fontFamily: SF Pro, fontSize: 12px, fontWeight: 400 }
  caption-2: { fontFamily: SF Pro, fontSize: 11px, fontWeight: 400 }
  editorial-title-1: { fontFamily: Georgia, fontSize: 28px, fontWeight: 400 }
  editorial-title-3: { fontFamily: Georgia, fontSize: 20px, fontWeight: 400 }
  editorial-callout: { fontFamily: Georgia, fontSize: 16px, fontWeight: 400 }
rounded:
  small: 4
  medium: 8
  large: 12
  x-large: 16
  xx-large: 24
  xxx-large: 32
  full: 9999
spacing:
  xx-small: 2
  x-small: 4
  small: 8
  medium: 12
  large: 16
  x-large: 24
  xx-large: 32
components:
  primary-button: { backgroundColor: "{colors.primary}", textColor: "{colors.on-primary}", typography: "{typography.headline-semibold}", rounded: "{rounded.full}", height: 46 }
  neutral-button: { backgroundColor: "{colors.background}", textColor: "{colors.primary}", typography: "{typography.headline-semibold}", rounded: "{rounded.full}", height: 46 }
  selectable-pill: { backgroundColor: "{colors.surface-subtle}", textColor: "{colors.on-surface}", typography: "{typography.subheadline-medium}", rounded: "{rounded.full}", padding: "{spacing.medium}" }
  article-row: { backgroundColor: "{colors.surface}", textColor: "{colors.on-surface}", typography: "{typography.callout}" }
  toast-card: { backgroundColor: "{colors.surface}", textColor: "{colors.on-surface}", typography: "{typography.subheadline}", rounded: "{rounded.xx-large}", padding: "{spacing.large}" }
x-stag:
  schema: 1
  platform: ios
  peer: none
  facts:
    ui_framework: { primary: mixed, swiftui_files: 270, uikit_files: 351 }
    deployment_target: "17.6"
    token_source: code
    generated: false
    accessor: "WMFAppEnvironment.current.theme.<semanticProperty>"
    dark_mode:
      status: user
      mechanism: "The user selects Default, Light, Sepia, Dark, or Black; WMFAppEnvironment distributes the resolved WMFTheme and component hosts override the interface style."
      evidence:
        - WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift
        - WMFComponents/Sources/WMFComponents/Environment/WMFAppEnvironment.swift
        - Wikipedia/Code/AppearanceSettingsViewController.swift
    spacing_scale: "WMFSpacing: 2, 4, 8, 12, 16, 24, 32"
    liquid_glass: { call_sites: 91, behavior: "Native iOS 26 glass is used when available, with themed fallbacks on earlier iOS versions." }
    dynamic_color: "Theme values are distributed in code rather than adaptive asset colors."
    migration: "WMFComponents is canonical for new UI; the legacy WMF Framework Theme remains compatibility code."
    confirmed:
      app_feel: "Quiet, trustworthy, and content-first — editorial rather than decorative, with restrained color and motion."
      canonical_system: "Use WMFComponents as canonical; treat the older theme layer as compatibility code during migration."
      adhoc_values: "Promote repeated one-off values into the system when they appear across multiple features."
  themes:
    default: light
    selection: system_and_user
    list:
      - { id: light, kind: appearance }
      - { id: sepia, kind: appearance }
      - { id: dark, kind: appearance }
      - { id: black, kind: appearance }
  values:
    colors.primary: { sepia: "#3366CC", dark: "#6699FF", black: "#6699FF" }
    colors.on-primary: { sepia: "#F8F1E3", dark: "#27292D", black: "#000000" }
    colors.accent: { sepia: "#00AF89", dark: "#00AF89", black: "#00AF89" }
    colors.on-surface: { sepia: "#202122", dark: "#F8F9FA", black: "#F8F9FA" }
    colors.on-surface-secondary: { sepia: "#646059", dark: "#C8CCD1", black: "#C8CCD1" }
    colors.surface: { sepia: "#F8F1E3", dark: "#27292D", black: "#000000" }
    colors.surface-subtle: { sepia: "#F0E6D6", dark: "#202122", black: "#202122" }
    colors.background: { sepia: "#E1DAD1", dark: "#101418", black: "#101418" }
    colors.surface-popover: { sepia: "#F8F1E3", dark: "#101418", black: "#202122" }
    colors.chrome: { sepia: "#F8F1E3", dark: "#2E3136", black: "#2E3136" }
    colors.outline: { sepia: "#CBC8C1", dark: "#2E3136", black: "#27292D" }
    colors.outline-subtle: { sepia: "#CBC8C1", dark: "#72777D", black: "#72777D" }
    colors.icon: { sepia: "#646059", dark: "#C8CCD1", black: "#C8CCD1" }
    colors.icon-background: { sepia: "#E1DAD1", dark: "#27292D", black: "#27292D" }
    colors.error: { sepia: "#B32424", dark: "#DD3333", black: "#DD3333" }
    colors.warning: { sepia: "#FF9500", dark: "#FFCC33", black: "#FFCC33" }
    colors.success: { sepia: "#14866D", dark: "#14866D", black: "#14866D" }
    colors.secondary-action: { sepia: "#2A4B8D", dark: "#2A4B8D", black: "#2A4B8D" }
    colors.selection: { sepia: "#EAF3FF", dark: "#2A4B8D", black: "#2A4B8D" }
    colors.tag: { sepia: "#FFFFFF", dark: "#FFFFFF", black: "#FFFFFF" }
    colors.tag-background: { sepia: "#6699FF", dark: "#6699FF", black: "#6699FF" }
    colors.scrim: { sepia: "#64605999", dark: "#000000BF", black: "#000000BF" }
  bindings:
    colors.primary: { native: "WMFAppEnvironment.current.theme.link", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#link" }
    colors.on-primary: { native: "WMFAppEnvironment.current.theme.paperBackground", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#paperBackground" }
    colors.accent: { native: "WMFAppEnvironment.current.theme.accent", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#accent" }
    colors.on-surface: { native: "WMFAppEnvironment.current.theme.text", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#text" }
    colors.on-surface-secondary: { native: "WMFAppEnvironment.current.theme.secondaryText", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#secondaryText" }
    colors.surface: { native: "WMFAppEnvironment.current.theme.paperBackground", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#paperBackground" }
    colors.surface-subtle: { native: "WMFAppEnvironment.current.theme.midBackground", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#midBackground" }
    colors.background: { native: "WMFAppEnvironment.current.theme.baseBackground", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#baseBackground" }
    colors.surface-popover: { native: "WMFAppEnvironment.current.theme.popoverBackground", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#popoverBackground" }
    colors.chrome: { native: "WMFAppEnvironment.current.theme.chromeBackground", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#chromeBackground" }
    colors.outline: { native: "WMFAppEnvironment.current.theme.border", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#border" }
    colors.outline-subtle: { native: "WMFAppEnvironment.current.theme.newBorder", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#newBorder" }
    colors.icon: { native: "WMFAppEnvironment.current.theme.icon", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#icon" }
    colors.icon-background: { native: "WMFAppEnvironment.current.theme.iconBackground", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#iconBackground" }
    colors.error: { native: "WMFAppEnvironment.current.theme.destructive", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#destructive" }
    colors.warning: { native: "WMFAppEnvironment.current.theme.warning", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#warning" }
    colors.success: { native: "WMFAppEnvironment.current.theme.successGreen", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#successGreen" }
    colors.secondary-action: { native: "WMFAppEnvironment.current.theme.secondaryAction", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#secondaryAction" }
    colors.selection: { native: "WMFAppEnvironment.current.theme.batchSelectionBackground", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#batchSelectionBackground" }
    colors.tag: { native: "WMFAppEnvironment.current.theme.tagText", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#tagText" }
    colors.tag-background: { native: "WMFAppEnvironment.current.theme.tagBackground", source: "WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift#tagBackground" }
    typography.body: { native: "WMFFont.for(.body)", source: "WMFComponents/Sources/WMFComponents/Style/WMFFont.swift#body" }
    typography.callout: { native: "WMFFont.for(.callout)", source: "WMFComponents/Sources/WMFComponents/Style/WMFFont.swift#callout" }
    typography.subheadline: { native: "WMFFont.for(.subheadline)", source: "WMFComponents/Sources/WMFComponents/Style/WMFFont.swift#subheadline" }
    typography.footnote: { native: "WMFFont.for(.footnote)", source: "WMFComponents/Sources/WMFComponents/Style/WMFFont.swift#footnote" }
    rounded.small: { native: "WMFCornerRadius.small", source: "WMFComponents/Sources/WMFComponents/Style/WMFCornerRadius.swift#small" }
    rounded.medium: { native: "WMFCornerRadius.medium", source: "WMFComponents/Sources/WMFComponents/Style/WMFCornerRadius.swift#medium" }
    rounded.large: { native: "WMFCornerRadius.large", source: "WMFComponents/Sources/WMFComponents/Style/WMFCornerRadius.swift#large" }
    rounded.x-large: { native: "WMFCornerRadius.xLarge", source: "WMFComponents/Sources/WMFComponents/Style/WMFCornerRadius.swift#xLarge" }
    spacing.small: { native: "WMFSpacing.small", source: "WMFComponents/Sources/WMFComponents/Style/WMFSpacing.swift#small" }
    spacing.medium: { native: "WMFSpacing.medium", source: "WMFComponents/Sources/WMFComponents/Style/WMFSpacing.swift#medium" }
    spacing.large: { native: "WMFSpacing.large", source: "WMFComponents/Sources/WMFComponents/Style/WMFSpacing.swift#large" }
  fonts:
    - { family: SF Pro, files: [], registered_via: system, installed_on_mac: true, preview: system, used_by: "Interface, controls, and navigation" }
    - { family: Georgia, files: [], registered_via: system, installed_on_mac: true, preview: system, used_by: "Editorial headings and article emphasis" }
    - { family: EB Garamond, files: [WMFComponents/Sources/WMFComponents/Resources/EBGaramond-Medium.ttf], registered_via: bundle-module-runtime, preview: load_from_repo, used_by: "Year in Review" }
    - { family: Wikipedia, files: [Wikipedia/logo-wikipedia.ttf], registered_via: UIAppFonts, preview: load_from_repo, used_by: "Wordmark glyphs" }
  examples:
    - { screen: Reading appearance themes, path: Wikipedia/Code/AppearanceSettingsViewController.swift, shows: [light, sepia, dark, black, user-selection] }
    - { screen: For You settings, path: WMFComponents/Sources/WMFComponents/Components/Settings/Home/For You/WMFHomeFeedForYouSettingsView.swift, shows: [themed-list, section-labels, chrome] }
    - { screen: Article row, path: WMFComponents/Sources/WMFComponents/Components/Shared/Page/WMFPageRow.swift, shows: [content-hierarchy, thumbnail, swipe-actions] }
    - { screen: Shared capsule buttons, path: WMFComponents/Sources/WMFComponents/Components/Shared/Buttons/CapsuleButtonStyle.swift, shows: [primary, neutral, quiet, glass, dynamic-type-growth] }
    - { screen: Toast card, path: WMFComponents/Sources/WMFComponents/Components/Shared/Toasts/WMFToastCardView.swift, shows: [glass, fallback-surface, depth, thumbnail] }
  known_off_system:
    - { id: hardcoded-color-literals, pattern: "UIColor/Color values declared directly in feature code", count: 48, replacement: "Promote repeated roles into WMFTheme and WMFColor; keep unique artwork colors local." }
  sizes:
    - { kind: button, name: capsule-button, height: 46, radius: 9999 }
    - { kind: pill, name: selectable-pill, radius: 9999, inset: 13 }
    - { kind: media, name: article-row-thumbnail, width: 40, height: 40, radius: 4 }
    - { kind: media, name: toast-thumbnail, width: 45, height: 45, radius: 8 }
    - { kind: icon, name: toast-symbol, width: 30, height: 30 }
    - { kind: other, name: toast-card, radius: 24, inset: 20 }
    - { kind: margin, name: standard-content-margin, inset: 16 }
  roles:
    primary: accent
    on-primary: text
    accent: accent
    on-surface: text
    on-surface-secondary: textSecondary
    surface: surface
    surface-subtle: surface
    background: background
    outline: border
    error: error
    scrim: scrim
  usage:
    primary: "Links, primary actions, and selected controls."
    accent: "Wikipedia green emphasis where the feature explicitly calls for it."
    surface: "Primary reading and card surface."
    surface-subtle: "Grouped content and secondary section surface."
    background: "Lowest-level canvas behind grouped surfaces."
    on-surface: "Primary readable content."
    on-surface-secondary: "Descriptions, metadata, and section labels."
  gaps:
    - "Typography consolidates italic and bold-italic variants into their base size and weight roles to keep the shared role set usable."
    - "Editor heading sizes and Helvetica variants remain specialist styles in WMFFont rather than general-purpose roles."
    - "The project contains targets at iOS 16.6 and 17.6; 17.6 is the main app target baseline reflected here."
    - "The legacy theme has widget-only variants that are not WMFComponents appearance themes and are intentionally excluded."
    - "The repository scan found 48 direct color literals; repeated values should be promoted, while unique illustration and animation colors remain local."
  deviations: none
  generated_from:
    at: 2026-11-18T06:38:12Z
    inputs:
      - path: WMFComponents/Sources/WMFComponents/Style/WMFColor.swift
        sha256: 08ddd633658734b5475bf111f60814719b52c059def6fbed75e2cede4163cad1
      - path: WMFComponents/Sources/WMFComponents/Style/WMFTheme.swift
        sha256: 618af322b96a0651bd3a49889fd75486ce4e9d95278c873591ab43a250fe2aec
      - path: WMFComponents/Sources/WMFComponents/Style/WMFFont.swift
        sha256: a3e67cd64fd4472d4a720dfb3b8b647df815aa3b26027eea1176d318849b0b54
      - path: WMFComponents/Sources/WMFComponents/Style/WMFSpacing.swift
        sha256: e1faeeeed271d79fa96ce4b0bcd4c8aa21e52829c2f718be68f1036e305c9b62
      - path: WMFComponents/Sources/WMFComponents/Style/WMFCornerRadius.swift
        sha256: c3bd7da602a4c9a5227c810366f28100775dd72d45e8c191c01bd74a0caf56f0
      - path: WMFComponents/Sources/WMFComponents/Environment/WMFAppEnvironment.swift
        sha256: 3bab0eb065500ad073bb4ffe3880b7aa321847b93777da2082b2d4913822b1ef
      - path: WMFComponents/Sources/WMFComponents/Components/Shared/Buttons/WMFLargeButton.swift
        sha256: 05201c80359947fef54f96300495ff26b83a48c0d117b270d4758d0832cf819f
      - path: WMFComponents/Sources/WMFComponents/Components/Shared/Buttons/CapsuleButtonStyle.swift
        sha256: 88034d41f98e200175e0f969e286c2eb70913ec2847d32b2aba08c26af66a6c3
      - path: WMFComponents/Sources/WMFComponents/Components/Shared/Buttons/WMFMediumButton.swift
        sha256: 2b7b6f4df319763597a26ea162e835ad82dad33ea885e8d374b89cc97a8c9ff3
      - path: WMFComponents/Sources/WMFComponents/Components/Shared/Buttons/WMFSmallButton.swift
        sha256: 7c6bd327fea71715272bf94657404cee7a6fde92ac872b25d5ce88e33691fd9c
      - path: WMFComponents/Sources/WMFComponents/Components/Shared/Buttons/WMFSelectablePillButton.swift
        sha256: a514e1be3daa71ea3f793ef42a84cb08a0198952b5e3758e50a28f15c12aba3c
      - path: WMFComponents/Sources/WMFComponents/Components/Shared/Page/WMFPageRow.swift
        sha256: 450386250195a0b2f1f8a065c6897b483f32bdc0edd5f35e30184c9a045ecb84
      - path: WMFComponents/Sources/WMFComponents/Components/Shared/Toasts/WMFToastCardView.swift
        sha256: 05dd23ca8e4cc198d144df5ce54eee6e6b9b1fc63d28033641748a282cb27afa
      - path: WMFComponents/Sources/WMFComponents/Components/Settings/Home/For You/WMFHomeFeedForYouSettingsView.swift
        sha256: c429994e20c5cd2fabc77fcafd7f16e29e1508b7cb927d03f70985c8401d9acb
      - path: WMF Framework/Theme.swift
        sha256: 0bc89b6c62eb8914f9593aa1e111a91d2a3a9d877289a85f2ed2af32414c4475
      - path: Wikipedia/Code/AppearanceSettingsViewController.swift
        sha256: e69259de67445b25726a365ebc39901bb9d01bf87362c21ca5791d48c74ccf63
      - path: Wikipedia.xcodeproj/project.pbxproj
        sha256: 05be613683cd27c9ab2d4df1e3f97b231bfa7fc2faa0d161f8740ee66712c0d3
      - path: Wikipedia/Alpha-Info.plist
        sha256: b7ce359704d13c1f9a37d1b2db2defb4d89532246ede194b7f96200a252a8d9e
      - path: Wikipedia/Wikipedia-Info.plist
        sha256: 6892f45cbf199bb2e0cea1ed841ba64e23f769c11fce7e0bab1bbf97cf0fcbee
      - path: Wikipedia/Experimental-Info.plist
        sha256: 736c360b33e39f122d51053fc146a7bbe912a70028b853ad322d7e58cf7b60d3
      - path: WMFComponents/Sources/WMFComponents/Components/Year in Review/WMFYearInReviewEndView.swift
        sha256: 9d449bb2eb48e3a6f27b7463d983d67b9b1bee7cb457ac2b73f219afeac51902
      - path: WMFComponents/Sources/WMFComponents/Components/Shared/Rive/WMFRiveWorkerProvider.swift
        sha256: f10a6ee96caf6102c11d0b216920f81388b301deb83d32798464c8872fcdc2c6
---
## Overview

- Keep new UI quiet, trustworthy, and content-first—editorial rather than decorative, with restrained color and motion.
- Make reading and comprehension the visual priority; let controls recede until needed.
- Build new screens from WMFComponents. Treat the older app theme layer only as migration compatibility.

## Colors

- Read semantic colors from `WMFAppEnvironment.current.theme`; never branch on a theme name inside a component.
- Support Light, Sepia, Dark, and Black with the values declared in `WMFTheme`.
- Use blue for links, primary actions, and selection. Reserve green for explicit accent or success roles.
- Promote a feature color only after the same visual job repeats across features.

## Typography

- Use `WMFFont.for(...)` so text follows Dynamic Type.
- Prefer SF Pro for interface text and Georgia for editorial emphasis.
- Preserve the standard iOS hierarchy: titles, headline or body, then subheadline, footnote, and captions.
- Keep specialist display fonts inside the feature that owns them.

## Layout

- Use the 2–32 point `WMFSpacing` scale for gaps and padding.
- Default content margins and card padding to 16 points; use 24 points between major sections.
- Let controls grow for larger accessibility text instead of clipping labels.

## Elevation & Depth

- Keep ordinary content flat and separated by surface changes or subtle outlines.
- Use native Liquid Glass for iOS 26 navigation, buttons, and transient overlays where the existing component supports it.
- Preserve the themed solid fallback on earlier iOS versions.

## Shapes

- Use capsules for actions and single-choice pills.
- Use the shared corner-radius scale for thumbnails, callouts, and cards.
- Match radius to hierarchy: 4–8 for media, 12–16 for controls and cards, and 24–32 for prominent containers.

## Components

- Reuse the shared capsule button styles for primary, neutral, quiet, and glass actions.
- Use `WMFPageRow` patterns for article title, description, thumbnail, and contextual actions.
- Configure navigation through WMFComponent navigation controllers rather than one-off SwiftUI navigation styling.
- Keep theme, Dynamic Type, accessibility labels, and large-text growth intact when composing shared components.

## Do's and Don'ts

- Do use semantic theme properties, `WMFFont`, `WMFSpacing`, `WMFCornerRadius`, and the shared icon APIs.
- Do promote repeated feature values into the responsible shared token or component.
- Do keep unique artwork, animation, and campaign colors local to their owning feature.
- Don't introduce new UI through the legacy theme API.
- Don't hard-code light colors, fixed text sizes, or a color-scheme assumption.
- Don't add decorative depth or motion that competes with article content.
