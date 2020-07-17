# Erasmus Mundus Master of Science in Public Sector Innovation and eGovernance (PIONEER) 
- [Ku Leuven University - Belgium](https://www.kuleuven.be/kuleuven/)
- [University of Münster - Germany](https://www.uni-muenster.de/en/)
- [Taltech University of Technology  - Estonia](https://www.taltech.ee)

## Integrated Research Seminar - Cross Border Service group

Date of submission: 2020-07-17

## Sharing dynamic ICU data across cross-border systems: a semantic data model and an OpenAPI specification

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

 
Moreover, this is not a new development in the healthcare sector but has been intensively taking place before (Smith, 1999). In general, health information systems (HIS) have been developed in many national and lower level contexts, not only for emergencies but also to improve, assess and facilitate health care (Magnuson & Fu, Jr., 2014). Systems associated with data collection or health management information systems on the international level are offered by several organizations such as the WHO, OECD, and EU (Grassi & Bolognini, 2017). Especially on the European Union has made efforts to improve the availability of qualitative health data across Europe (Tania et al., 2012). However, the creation of numerous national platforms during the COVID-19 crisis to provide relevant information has shown that firstly, before the relevant information was not openly available and secondly, an existing cross border system was not in place in order to share this information easily. 

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

--- 
### References:


Aimé, X., Traore, L., Chniti, A., Sadou, E., Ouagne, D., Charlet, J., Jaulent, M. C., Darmoni, S., Griffon, N., Amardeilh, F., Bascarane, L., Lepage, E., & Daniel, C. (2015b). Semantic interoperability platform for healthcare information exchange. Irbm, 36(2), 62–69. https://doi.org/10.1016/j.irbm.2015.01.003 

Barbarito, F., Pinciroli, F., Mason, J., Marceglia, S., Mazzola, L., & Bonacina, S. (2012). Implementing standards for the interoperability among healthcare providers in the public regionalized Healthcare Information System of the Lombardy Region. Journal of Biomedical Informatics, 45(4), 736–745. https://doi.org/10.1016/j.jbi.2012.01.006 

Batra, U., Sachdeva, S., & Mukherjee, S. (2015a). Implementing healthcare interoperability utilizing SOA and data interchange agent. Health Policy and Technology, 4(3), 241–255. https://doi.org/10.1016/j.hlpt.2015.04.005 

Batra, U., Sachdeva, S., & Mukherjee, S. (2015b). Implementing healthcare interoperability utilizing SOA and data interchange agent. Health Policy and Technology, 4(3), 241–255. https://doi.org/10.1016/j.hlpt.2015.04.005 

Chen, Y., Brown, S. A., Hu, P. J., King, C., Chen, H., Chen, Y., Brown, S. A., King, C., & Chen, H. (2011). Managing Emerging Infectious Diseases with Information Systems : Reconceptualizing Outbreak Management Through the Lens of Loose Coupling Managing Emerging Infectious Diseases with Information Systems : Reconceptualizing Outbreak Management Through the Le. June 2020. 

Daiqin, D., Jian, H., Compton, M., & Taylor, K. (2012). Authorization in cross-border eHealth systems. 43–55. https://doi.org/10.1007/s10796-011-9316-y 

Dehnavieh, R., Khajeh, Z., & Hasani, M. (2019). The District Health Information System ( DHIS2 ): A literature review and meta- synthesis of its strengths and operational challenges based on the experiences of 11 countries. 48(2), 62–75. https://doi.org/10.1177/1833358318777713 

Dogac, A. (2012). Interoperability in eHealth Systems. Proceedings of the VLDB Endowment, 5(12), 2026–2027. https://doi.org/doi/10.14778/2367502.2367568 

EC. (2020). Guidelines on EU Emergency Assistance in Cross-Border Cooperation in Healthcare related to the COVID-19 crisis. In COMMUNICATION FROM THE COMMISSION. https://ec.europa.eu/info/sites/info/files/guidelines_on_eu_emergency_assistance_in_cross-bordercooperationin_heathcare_related_to_the_covid-19_crisis.pdf 

ECDC. (2020). European Center for Disease Prevention and Control. Coronavirus disease 2019 (COVID-19) pandemic: increased transmission in the EU/EEA and the UK – seventh update. In European Center for Disease Prevention and Control (Vol. 1, Issue ECDC). https://www.ecdc.europa.eu/sites/default/files/documents/RRA-seventh-update-Outbreak-of-coronavirus-disease-COVID-19.pdf 

Edmunds, M. (2014). Governmental and legislative context of informatics. In Public health informatics and information systems (pp. 47–66). Springer. 

eHealth Network. (2015). Redefined eHealth European Interoperability Framework (Vol. 5, Issue 22). https://ec.europa.eu/health/sites/health/files/ehealth/docs/ev_20151123_co03_en.pdf 

European Commission. (2017). New European Interoperability Framework - Promoting seamless services and data flows for European public administrations. In European commision (Vol. 32, Issue 9). https://doi.org/10.2799/78681 

European Commission - Semic Team. (n.d.). About DCAT Application Profile for data portals in Europe. Retrieved June 28, 2020, from https://joinup.ec.europa.eu/collection/semantic-interoperability-community-semic/solution/dcat-application-profile-data-portals-europe/about 

European Commission, D. (2020). IMAPS: assess the interoperability maturity of your digital public service. https://ec.europa.eu/isa2/news/imaps-assess-interoperability-maturity-your-digital-public-service_en 

Grassi, T., & Bolognini, A. (2017). Cost/benefit analysis of a sustainable EU Health Information system. https://op.europa.eu/en/publication-detail/-/publication/ed1f7697-6141-11e7-8dc1-01aa75ed71a1 

Gupta, A., Patel, V. L., & Greenes, R. A. (2016). Advances in Healthcare Informatics and Analytics. https://doi.org/10.1007/978-3-319-23294-2 

He, D. D., Yang, J., Compton, M., & Taylor, K. (2012). Authorization in cross-border eHealth systems. Information Systems Frontiers, 14(1), 43–55. https://doi.org/10.1007/s10796-011-9316-y 

Heeks, R. (2006). Health information systems: Failure, success and improvisation. International Journal of Medical Informatics, 75(2), 125–137. https://doi.org/10.1016/j.ijmedinf.2005.07.024 

ISA - Interoperability solutions for public administrations,  businesses and citizens. (n.d.). Core Vocabularies. Retrieved July 2, 2020, from https://ec.europa.eu/isa2/solutions/core-vocabularies_en# 

ISA2 European Commission. (2019). ISA2 WORK PROGRAMME 2019: DETAILED DESCRIPTION OF ACTIONS PART 2/2. https://ec.europa.eu/isa2/sites/isa/files/docs/pages/isa2_wp_2019_detailed_descriptions_part_2.pdf 

Magnuson, J. A., & Fu, Jr., P. C. (2014). Public Health Informatics and Information Systems. In J. A. Magnuson & P. C. Fu, (Eds.), London : Springer London : Imprint Springe (Vol. 25, Issue 2). Springer London. https://doi.org/10.1007/978-1-4471-4237-9 

Maresi, I. (2020). A data engineer’s guide to semantic modelling. https://zenodo.org/record/3898519#.XwG4Z5P7QWq 

Noy, N. F., & McGuinness, D. L. (2001). Ontology development 101: A guide to creating your first ontology. Stanford knowledge systems laboratory technical report KSL-01-05 and …. 

Olson, D., Leitheiser, A., Atchison, C., Larson, S., & Homzik, C. (2005). Public health and terrorism preparedness: Cross-border issues. Public Health Reports, 120(SUPLL. 1), 76–83. https://doi.org/10.1177/00333549051200s115 

PCM/DPC. (n.d.). GitHub- pcm-dpc / Covid 19. Retrieved July 10, 2020, from https://github.com/pcm-dpc/COVID-19 

Perkel, J. M. (2020). Behind the Johns Hopkins University coronavirus dashboard. Natur Index. 

President of the council of Ministers Italy. (n.d.). Urgent measures regarding the containment and management of the epidemiological emergency from COVID-19, applicable on the whole national territory. In Official Gazzete Italy. 

PwC EU Services. (2015). e-Government Core Vocabularies handbook: Using horizontal data standards for promoting interoperability: This report was prepared for the ISA Programme by: PwC~EU~services. European Commission. https://joinup.ec.europa.eu/site/core_vocabularies/Core_Vocabularies_user_handbook/ISA Hanbook for using Core Vocabularies.pdf 

Research Data Alliance FAIR Data Maturity Model Working Group. (2020). FAIR Data Maturity Model: specification and guidelines - draft. Research Data Alliance. https://doi.org/10.15497/RDA00045 

Sadeghi, P., Benyoucef, M., & Kuziemsky, C. E. (2012). A mashup based framework for multi level healthcare interoperability. 57–72. https://doi.org/10.1007/s10796-011-9306-0 

Shekelle, P. G., Morton, S. C., & Keeler, E. B. (2006). COSTS AND BENEFITS OF HEALTH INFORMATION TECHNOLOGY (Issue April). 

Smith, J. (1999). Health Management Information Systems: A handbook for decision makers. McGraw-Hill Education (UK). 

Swagger. (n.d.). OpenAPI Specification. Retrieved July 2, 2020, from https://swagger.io/specification/ 

Swagger Hub. (n.d.). OpenAPI 3.0 Tutorial. Retrieved July 3, 2020, from https://app.swaggerhub.com/help/tutorials/openapi-3-tutorial 

Tania, C., Iorio, D., Carinci, F., Brillante, M., Azzopardi, J., Beck, P., Bratina, N., Cunningham, S. G., Beaufort, C. De, & Debacker, N. (2012). Cross-border flow of health information : is ‘ privacy by design ’ enough ? Privacy performance assessment in EUBIROD. 23(2), 247–253. https://doi.org/10.1093/eurpub/cks043 

The eHealth Network. (2020). Towards a common approach for the use of anonymised and aggregated mobility data for modelling the diffusion of COVID-19, and optimising the effectiveness of response measures: Version 4.3. 

Thrasher, E. (2016). An empirical investigation of the impact of information technology integration in healthcare integrated delivery systems. In Advances in Healthcare Informatics and Analytics (pp. 125–144). Springer. 

Vogel, D., Guo, X., Linger, H., Barry, C., Lang, M., & Schneider, C. (2016). Lecture Notes in Information Systems and Organisation 17 Transforming Healthcare Through Information Systems. https://doi.org/10.1007/978-3-319-30133-4 

Wilkinson, M. D., Dumontier, M., Aalbersberg, I. J. J., Appleton, G., Axton, M., Baak, A., Blomberg, N., Boiten, J.-W., da Silva Santos, L. B., Bourne, P. E., Bouwman, J., Brookes, A. J., Clark, T., Crosas, M., Dillo, I., Dumon, O., Edmunds, S., Evelo, C. T., Finkers, R., … Mons, B. (2016). The FAIR Guiding Principles for scientific data management and stewardship. Scientific Data, 3, 160018. https://doi.org/10.1038/sdata.2016.18 

World Health Organization. (2020). Maintaining essential health services: operational guidance for the COVID-19 context (Issue June). 

 
