---
type: PageLayout
title: About
colors: colors-a
backgroundImage:
  type: BackgroundImage
  url: /images/bg4.jpg
  backgroundSize: cover
  backgroundPosition: center
  backgroundRepeat: no-repeat
  opacity: 75
sections:
  - elementId: ''
    colors: colors-f
    backgroundSize: full
    text: >+

      I have a track record of creating high-value dashboards and reports using
      tools like MSSQL, Tableau, Power BI, Python, and Excel. In my role, I have
      monitored crucial KPIs, with a financial approach that helps the company
      make the best decisions from this perspective, contributing to operational
      excellence. In my previous roles, I have leveraged various tools to
      produce top-quality panels and reports for operational and financial KPIs,
      emphasizing process automation to drive insights and improve productivity.




    media:
      type: ImageBlock
      url: /images/sebs.jpg
      altText: Hero image
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
          - pt-16
          - pb-12
          - pl-4
          - pr-4
        justifyContent: center
      title:
        textAlign: left
      subtitle:
        textAlign: left
      text:
        textAlign: left
      actions:
        justifyContent: flex-start
    type: HeroSection
  - type: DividerSection
    styles:
      self:
        width: wide
        padding:
          - pt-12
          - pb-12
          - pl-4
          - pr-4
        justifyContent: center
        borderWidth: 1
        borderStyle: solid
  - type: LabelsSection
    colors: colors-f
    subtitle: ''
    items:
      - type: Label
        label: MS SQL
      - type: Label
        label: Power BI
      - type: Label
        label: Tableau
      - type: Label
        label: Python
      - type: Label
        label: Excel
    title: 'Skills:'
  - type: FeaturedItemsSection
    title: ''
    items:
      - type: FeaturedItem
        title: SQL
        subtitle: ''
        text: >+

          For ad-hoc reports and dashboards, use views and CTEs for custom
          queries.


        actions: []
        elementId: ''
        styles:
          self:
            textAlign: left
      - type: FeaturedItem
        title: Power BI & Tableau
        subtitle: ''
        text: |+
          For the development of dashboards to monitor key KPIs.


        actions: []
        elementId: ''
        styles:
          self:
            textAlign: left
      - type: FeaturedItem
        title: Python
        subtitle: ''
        text: >+
          ETL and data cleaning, using Pandas, NumPy, and libraries like
          scikit-learn and

          StatsModels for data analysis and predictive modeling

        actions: []
        elementId: ''
        styles:
          self:
            textAlign: left
      - type: FeaturedItem
        title: 'Excel '
        subtitle: ''
        text: >+
          Experienced in creating ad-hoc reports and automating processes using
          Macros

        elementId: ''
        styles:
          self:
            textAlign: left
    actions: []
    colors: colors-f
    columns: 1
    spacingX: 16
    spacingY: 16
    elementId: ''
    styles:
      self:
        height: auto
        width: narrow
        padding:
          - pt-28
          - pb-36
          - pl-4
          - pr-4
        justifyContent: center
      title:
        textAlign: left
      subtitle:
        textAlign: left
      actions:
        justifyContent: flex-start
  - type: DividerSection
    styles:
      self:
        width: wide
        padding:
          - pt-12
          - pb-12
          - pl-4
          - pr-4
        justifyContent: center
        borderWidth: 1
        borderStyle: solid
  - type: TextSection
    variant: variant-b
    subtitle: 'Contact: '
    colors: colors-f
    text: |
      Phone:+57 3153239201
      Mail:<johnsebas2@gmail.com>
    title: ''
  - type: DividerSection
    styles:
      self:
        width: wide
        padding:
          - pt-8
          - pb-8
          - pl-4
          - pr-4
        justifyContent: center
        borderWidth: 1
        borderStyle: solid
  - type: FeaturedItemsSection
    colors: colors-f
    items:
      - type: FeaturedItem
        subtitle: 'Experience:'
        text: >
          **Business Intelligence Analyst - Teleperformance**


          *   Developed and applied linear and logistic regression models using
          Python to predict key business metrics and customer behaviors,
          improving strategic decision-making and operational efficiency.


          **2022-2024**


          **Reporting Analyst - Logfor**


          *   Utilized tools like Excel to create high-impact reports, enabling
          the monitoring of critical KPIs.

          *   Assist in the implementation of Strategic systems, driving
          organizational growth.


          **2021-2022**
        styles:
          self:
            textAlign: left
            padding:
              - pt-0
              - pl-0
              - pb-0
              - pr-0
      - type: FeaturedItem
        subtitle: 'Education:'
        text: >
          **2017-2022**


          *   Business Administration with an emphasis on International Business


          ***


          Certificates:


          **2022**


          *   [Professional Certificate in Google Data
          Analytics](https://www.coursera.org/account/accomplishments/professional-cert/4BRX2D9UF6GA)


          **2022**


          *   [Data Analysis with Python: Zero to Pandas
          (2022)](https://jovian.ai/certificate/MFQTOOBVGI)


          **2023**


          *   [Advanced SQL Server Masterclass for Data
          Analysis](https://www.udemy.com/certificate/UC-bdfce6b1-61d1-4c3d-bccf-063ce61f3dc4/)
        styles:
          self:
            textAlign: left
            padding:
              - pt-0
              - pl-0
              - pb-0
              - pr-0
    columns: 2
    spacingX: 60
    spacingY: 60
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
          - pt-8
          - pb-8
          - pl-4
          - pr-4
        justifyContent: center
        borderRadius: none
        borderWidth: 0
        borderStyle: none
        borderColor: border-dark
      title:
        textAlign: left
      subtitle:
        textAlign: left
  - type: DividerSection
    styles:
      self:
        width: wide
        padding:
          - pt-12
          - pb-12
          - pl-4
          - pr-4
        justifyContent: center
        borderWidth: 1
        borderStyle: solid
  - type: ContactSection
    backgroundSize: full
    title: "Let’s talk... \U0001F4AC"
    colors: colors-f
    form:
      type: FormBlock
      elementId: sign-up-form
      fields:
        - name: firstName
          label: First Name
          hideLabel: true
          placeholder: First Name
          isRequired: true
          width: 1/2
          type: TextFormControl
        - name: lastName
          label: Last Name
          hideLabel: true
          placeholder: Last Name
          isRequired: false
          width: 1/2
          type: TextFormControl
        - name: email
          label: Email
          hideLabel: true
          placeholder: Email
          isRequired: true
          width: full
          type: EmailFormControl
        - name: message
          label: Message
          hideLabel: true
          placeholder: Tell me about your project
          isRequired: true
          width: full
          type: TextareaFormControl
      submitLabel: "Submit \U0001F680"
      styles:
        submitLabel:
          textAlign: center
    styles:
      self:
        height: auto
        width: narrow
        margin:
          - mt-0
          - mb-0
          - ml-4
          - mr-4
        padding:
          - pt-12
          - pb-12
          - pr-4
          - pl-4
        alignItems: center
        justifyContent: center
        flexDirection: row
      title:
        textAlign: left
      text:
        textAlign: left
---
