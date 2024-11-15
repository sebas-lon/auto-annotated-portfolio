---
type: PageLayout
title: case studies
sections:
  - type: HeroSection
    title: 'HI, I''M Sebas Londono'
    subtitle: >-
      An Business Intelligence Analyst with a strong desire to help
      organizations clearly state their needs and make meaningful changes
      through data-driven decisions.
    actions: []
    media:
      type: ImageBlock
      url: /images/1-370ee9d0.jpg
      altText: altText of the image
      caption: Caption of the image
      elementId: ''
    colors: colors-f
    backgroundSize: full
    elementId: ''
    styles:
      self:
        height: auto
        width: wide
        margin:
          - mt-0
          - mb-0
          - ml-0
          - mr-0
        padding:
          - pt-36
          - pb-48
          - pl-4
          - pr-4
        alignItems: center
        justifyContent: center
        flexDirection: row-reverse
      title:
        textAlign: left
      subtitle:
        textAlign: left
      text:
        textAlign: left
      actions:
        justifyContent: flex-start
  - type: FeaturedProjectsSection
    subtitle: Projects
    actions:
      - type: Link
        label: See all projects
        url: /projects
    projects:
      - content/pages/projects/aw-cycles.md
      - content/pages/projects/g4-analytics.md
      - content/pages/projects/placer-growth-analysis.md
    colors: colors-f
    variant: variant-b
    elementId: ''
    showDate: false
    showDescription: true
    showFeaturedImage: true
    showReadMoreLink: true
    styles:
      self:
        height: auto
        width: wide
        margin:
          - mt-0
          - mb-0
          - ml-0
          - mr-0
        padding:
          - pt-24
          - pb-24
          - pl-4
          - pr-4
        justifyContent: center
      title:
        textAlign: left
      subtitle:
        textAlign: left
      actions:
        justifyContent: flex-end
  - type: ContactSection
    title: "Got an interesting project? Tell me more...\U0001F4AC"
    form:
      type: FormBlock
      fields:
        - type: TextFormControl
          name: firstName
          label: First Name
          hideLabel: true
          placeholder: First Name
          width: 1/2
          isRequired: true
        - type: TextFormControl
          name: lastName
          label: Last Name
          hideLabel: true
          placeholder: Last Name
          width: 1/2
          isRequired: false
        - type: EmailFormControl
          name: email
          label: Email
          hideLabel: true
          placeholder: Email
          width: 1/2
          isRequired: true
        - type: TextFormControl
          name: address
          label: Address
          hideLabel: true
          placeholder: Address
          width: 1/2
          isRequired: true
      submitLabel: "Submit \U0001F680"
      elementId: sign-up-form
      styles:
        submitLabel:
          textAlign: center
    colors: colors-f
    backgroundSize: full
    styles:
      self:
        height: auto
        width: narrow
        margin:
          - mt-0
          - mb-0
          - ml-0
          - mr-0
        padding:
          - pt-24
          - pb-24
          - pr-4
          - pl-4
        alignItems: center
        justifyContent: center
        flexDirection: row
      title:
        textAlign: left
      text:
        textAlign: left
metaTags: []
colors: colors-a
backgroundImage:
  type: BackgroundImage
  url: /images/featured-Image4.jpg
  backgroundSize: cover
  backgroundPosition: right
  backgroundRepeat: no-repeat
  opacity: 30
---
