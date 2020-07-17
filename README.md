# Integrated Research Seminar 
# Cross Border Service group

Date of submission: 2020-07-17

## Sharing dynamic ICU data across cross-border systems: a semantic data model and an OpenAPI specification


---
Group members:

- Maria Claudia Bodino  

- Pablo Hartill Montalvo 

- Stefan Dedovic

- Viktor De Naeyer

Tutor: Dr. Hendrik Scholta

Supervisor: Prof. Dr. Dr. h.c Dr. h. c. Jörg Becker



---

## Introduction

Crises are often times of rethinking the current system and the breeding ground of innovation. Arguably one of the sectors most defined by and created for emergencies is the health sector. These health systems are designed to accommodate a certain expected amount of these emergencies. However, occasionally events happen, pushing the existing capacity over their limits. During the COVID-19 outbreak, health systems around the world found themselves struggling to handle the increased demand by COVID-19 patients while continuing to deliver essential services (World Health Organization, 2020). As a result, health organizations urged governments to take several measures in order to tackle this crisis, among which surveillance of indicators related to the disease (ECDC, 2020). This report by the European Centre for Disease Prevention and Control states that intensive care unit (ICU) data can be used as an indicator of the severity of the pandemic as well as to estimate the probability of dying. Additionally, the ECDC developed a transmission model of the virus to make forecasts of the cases as well as hospital requirements, among which ICU beds, based on intra-EU regional and cross-border flows (The eHealth Network, 2020) Consequently, mainly in the European context, countries were calling for cross-border cooperation between member states to contain the virus, alleviate the hardest hit health care systems, and save lives (EC, 2020). These calls to action show that there is a value in cross-border health data gathering systems. 

 
Moreover, this is not a new development in the healthcare sector but has been intensively taking place before (Smith, 1999). In general, health information systems (HIS) have been developed in many national and lower level contexts, not only for emergencies but also to improve, assess and facilitate health care (Magnuson & Fu, Jr., 2014). Systems associated with data collection or health management information systems on the international level are offered by several organizations such as the WHO, OECD, and EU (Grassi & Bolognini, 2017). Especially on the European Union has made efforts to improve the availability of qualitative health data across Europe (Tania et al., 2012). However, the creation of numerous national platforms during the COVID-19 crisis to provide relevant information has shown that firstly, before the relevant information was not openly available and secondly, an existing cross border system was not in place in order to share this information easily. Therefore, this paper is looking at “What are design recommendations for sharing dynamic ICU data in cross-border health information systems?”. As such, the goal of this paper is to examine the required data structure to facilitate cross-border health data sharing between nations by investigating cases and existing literature. 

 
The research covering this question is structured as followed, the next chapter describes the current state of research on this topic, starting with the process of identifying the relevant literature based on the main concepts, health information systems, and interoperability. This review lays the groundwork as well as defines the scope for the subsequent research. How the artifact is proposed, and the steps this research will execute is described in the research design. This chapter then leads to the results starting with an assessment of current regional and global cases to identify issues and practices, supporting the designing of the artifacts. The design of these health data sharing artifacts is described after that based on the gathered requirements and best practices in the literature review and state-of-the-art. The effects and improvements realized by this design are discussed after that, ending with concluding recommendations and directions for future research. 

--- 

## Artifact Design

### Sematic data model definition

The aim of this section is to propose a semantic data model representing the implicit meaning of the data trough defining the concepts (or classes), instances and relations within the data in order to provide a first attempt to model specific aspect of the pandemic related to the ICU bedding data at EU level. The information and properties of interest are based on the insights collected from the assessment of the case studies in section 4.3.  First, it is important to define briefly what a semantic model or ontology is: 

 
*“Semantic models of data sources represent the implicit meaning of the data by specifying the concepts and the relationships within the data.”(Maresi, 2020).* 

 
The objective of an ontology is to provide and define a common vocabulary for people who need to share information in a certain domain. An ontology includes machine-interpretable definitions of basic concepts in the domain and relations among them (Noy & McGuinness, 2001). Second, it is useful to emphasize some essential rules in a semantic model design: 

 
1. There is no one correct way to model a domain— there are always viable alternatives. The best solution almost always depends on the application that you have in mind and the extensions that you anticipate.  

2.  Ontology development is necessarily an iterative process.  

3. Concepts in the ontology should be close to objects (physical or logical) and relationships in your domain of interest. These are most likely to be nouns (objects) or verbs (relationships) in sentences that describe your domain” (Noy & McGuinness, 2001). 

 
For the purpose of this research, the term semantic model is equivalent to the term ontology.  

In order to build the edit, generate and visualize the semantic model, a popular free, open-source software, Protégé, is used23. Protégé was developed by the Standford Center for Biomedical Informatics Research at the Standford University School of Medicine for building intelligent systems and is supported by a strong community of academic, government, and corporate users build knowledge-based solutions in areas as diverse as biomedicine, e-commerce, and organizational modeling (Noy & McGuinness, 2001). 

 
Noy and McGuinness (2001), in the research Ontology Development 101: A guide to Creating your first ontology, suggest a list of basic steps to go over to get started with the model.  
 
The first steps consist of defining a list of competency questions to determine the domain and the scope of the semantic model, also known as “uses cases” to identify what the model will be used for clearly. 

The following Competency questions provided are based on the knowledge the authors gained from the literature review and the assessment of the cases, and they are not exhaustive: 

- Who is going to use the model?  

- Which information are relevant for identifying a hospital/clinic? 

- Is a hospital dataset provided at national and European level? 

- Which is the lowest level the information should be collected? 

- Which level of detail about domain-specific information – ICU should the model provide? 

- How to express ICU bed-related indicators? 

- Which time and geographical information should be delivered? 

Based on the competency questions, the researchers of the paper determined that the ontology needs to provide information both from a context- neutral data model and from a healthcare domain. These are some of the main concepts the research needs to model: 

- Hospital/clinic and departments/unit 

- Location – Territorial Geographical classification 

- Contact point of the hospital and departments/unit 

- Services located in the departments/unit 

- Indicators related to the availability of hospital ICU beds  

The second step consists in searching for existing ontologies that cover the domain of the research. Related to the scope of the research, providing cross-border public services across the EU is challenging because of the different peculiarities of the Member States, differences in terms of regulations, players and services (PwC EU Services, 2015). The authors of the paper had a deeper focus on the European Union initiatives from the Semantic Interoperability Community (SEMIC) that has the specific goal to provide a solution in the context of cross border services aligned with the EIF framework mentioned in the literature review. Furthermore, in order to map a data model, first, the research will focus on the Core Vocabularies defined by the ISA program of the European Commission in order to adopt a syntax neutral approach, independent of any technical representation that guarantees a minimum level of cross-border interoperability, semantic consistency and reduces schema-level conflict and inconsistency (ISA - Interoperability solutions for public administrations, n.d.). Additionally, the Core Vocabularies include the Dublin Core Metadata Set and the ISA Core Vocabularies. Therefore, the usage of Core Vocabularies in the definition of the current semantic model is a coherent and valid choice. 
 
More specifically, the following core vocabularies will be used in defining the data model: 

- Core Public Organization vocabulary (CPOV): to describe the entity of a hospital and clinic  

- Core Location Vocabulary (CLV): to model the fundamental characteristics of the location of the Hospital/clinic location. The Core Location Vocabulary is aligned with the INSPIRE data specifications. 

- A first draft of a controlled vocabulary “ICU Bed specifications” with the different type of ICU services provided. The first release of the controlled vocabularies contains the different service types of ICU beds that were found in the assessment.  Perhaps it is important to differentiate them between countries and key differences (as in the DIVI case). 

The first prototype of the semantic model and of the controlled dictionary is available under the following GitHub repository: https://github.com/PioneerMasterIRSCrossBorder/EU_ICU_indicators/Ontologies 

The Terse RDF Triple Language (Turtle, a syntax and file format for expressing data in the Resource Description Framework) resource is located under the folder “Ontologies/latest” and can be downloaded and navigated visually using WebVOWL, a web application available at the following link: http://www.visualdataweb.de/webvowl/   as in the figure presented below in Figure 5. Additionally, an offline version of the ontology in Turtle format is available in

---

### OPEN API Specification

OpenAPI Specification prototype 


As mentioned in the design research, many different actors, including health care professionals, researchers, policymakers, and citizens, need easy access to real time-critical data24. Based on the previous prototype of the semantic model presented, the researchers also aim to provide an additional prototype of an OpenAPI Specification (OAS) in order to suggest a second IT artifact that fulfills and provides a concrete technical tool to maximize the interoperability and reuse of the data from different actors with a standardised and programming language agnostic interface description. 

The OpenAPI Specification (OAS), also known as Swagger specification, is an open-source format and machine-readable file for describing and documenting Application Programming interfaces (APIs) (Swagger Hub, n.d.)25. 

 
As it is mentioned: “The OpenAPI Specification (OAS) defines a standard, language-agnostic interface to RESTful APIs which allows both humans and computers to discover and understand the capabilities of the service without access to source code, documentation, or through network traffic inspection. When properly defined, a consumer can understand and interact with the remote service with a minimal amount of implementation logic.” (Swagger, n.d.) (Swagger, Unknown).  

 

OAS is used by many developers and organizations for developing APIs, and it has become a de-facto standard for describing and designing RESTful APIs(Swagger, Unknown). The OpenAPI specifications can be written in JSON or YAML. The researchers decided to use YAML because it is easier to read and understand.  

 
As mentioned in the OpenAPI 3.0 Tutorial26 (Swagger Hub, Unknown), the main important aspects and part of an OpenAPI Specification are the following:  

- Meta information 

- Path items (endpoints): 

Parameters 

Request bodies 

Responses 

- Reusable components: 

Schemas (data models) 

Parameters 

Responses 

Other components 

Path items are particularly important in order to quickly understand which resources the API will provide; they represent the endpoints under it is possible to specify HTTP verbs for obtaining the available resources (Swagger Hub, Unknown). 

 
In particular, the following path (URL) will be available: 

```
- ICUdata-services/  
 
Retrieve the controlled vocabulary with the different ICU services available. 

- ICUdata/  

Retrieve the ICU date related to the three administrative levels available in NUTS classifications. It is possible to retrieve data in a specific time range. 

/country/{country_code}? 

/country/{country_code}/{admin_level_1} 

/country/{country_code}/{admin_level_1}/{admin_level_2} 

/country/{country_code}/{admin_level_1}/{admin_level_2} /{admin_level_3} 

 - Hospitals/ 

Retrieve the info related to a specific hospital and unit (contact point and address information). In order to query a single hospital, it is necessary to express the country which the hospital belongs to. For every country, a dataset containing the list and ids of every hospital and clinic should be provided. 

 
/country/{country_code}/hospital/{hospital_id} 

```

A final note is about the geographical classification that can be used in the model and consequently in the API. Related to the purpose of the research, a cross-border classification is represented by the NUTS classification (Nomenclature of territorial units for statistics) provided by Eurostat that provides a hierarchical system also based on population thresholds for the purpose of socio-economic analyses of the regions dividing regions at three different levels (NUTS 1, 2 and 3 respectively, moving from larger to smaller territorial units)27. Furthermore, Eurostat publishes the NUTS classification in Linked Data28 and a navigable version of the classification is provided at the following link: https://ipsoeu.github.io/ramon-ld/nuts  

