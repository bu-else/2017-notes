# BU ELSE 2017 - Project Descriptions
This file contains brief, high-level project descriptions. There are also suggestions and ideas about what technologies, libraries, and tools may be useful in building software artifacts that meet the requirements of each project.

## Drug Overdose Intervention App

*Credits*: Abby Rudolph (Assistant Professor of Epidemiology, BU School of Public Health)

Unintentional poisoning, primarily from drug overdose, is the leading cause of injury-related death among Americans. However, individuals may not be willing to report an overdose via 911 due to fear of interacting with law enforcement. This project involves creating a cross-platform mobile application whose primary functionality allows users to notify authorities anonymously that someone is suffering from an overdose in a particular location. The app also aims to help users identify someone nearby that is carrying Naloxone (a medication that can block the effects of opioids).

Possible technologies that may be useful include:
* [Ionic](https://ionicframework.com/)
* [Google Maps Plugin](https://ionicframework.com/docs/native/google-maps/) for Ionic or [Leaflet](http://leafletjs.com/)
* [Firebase](https://firebase.google.com/) or [MongoDB](https://www.mongodb.com/) (with [hapi](https://hapijs.com/) or [Frame](https://jedireza.github.io/frame/))
* [Twilio](https://www.twilio.com/)

Non-functional requirements (brainstorm):
* Logging
  * Location over time (or do not log until someone opts in if there is an emergency in the same general area)
  * Panic button usage
  * Log actual call events (could this discourage users?)
  * Log locally or on server?
* Storage
  * No major storage issues
  * Do we need proof of credentials (or that you are carrying Naloxone)? How is this stored and where?
* Configuration
  * Privacy settings depending on features
  * Back-end service that enables communication may need to be configurable
* Performance
  * Communication needs to happen quickly
  * App should be responsive
  * If polling is being used, will this impact bandwidth/other communications resources
* Cost
  * Small amount of data will need to be hosted
  * Small amount of bandwidth
  * Texting costs (or any third-party services that enable these features)
  * Insurance/legal costs
  * Assembling appropriate terms of use/end-user license agreements
* Interoperability: does it need to work with other services or frameworks
  * Third-party service for handling texting features
* Flexibility
  * Licensing of the code
* Accessibility
  * What is the target user population; should we support accessibility to a variety of populations?
  * How will this be distributed (probably app stores)
* Security
  * Will the backend service record any identifying information about users (location, phone, name, etc.)\
  * Should user information be encrypted (keyholder could be user or service provider)
* Disaster recovery
  * Service provider: should back everything up
  * Users: where will user state be stored (local phone or server) and can users recover it (e.g., using registration/authentication); should the app have a lock feature

## Boston Public Schools Bus Routing Scoreboard

*Credits*: Will Eger (Strategic Project Manager, Boston Public Schools)

The Boston Public Schools recently organized a [challenge](https://www.bostonpublicschools.org/transportationchallenge) focused on reducing the cost of running a fleet of school buses to transport students to and from school every day. While the initial contest is now over, they are interested in maintaining a continuous version of the challenge that allows anyone to submit candidate solutions for evaluation and scoring. This requires the creation of an interactive website that provides a copy of the challenge data, allows users to submit their candidate solutions, and keeps track of the best solutions on a scoreboard.

This project requires the assembly of a front-end website that can parse and display an Excel spreadsheet, run an algorithm to validate and evaluate the submitted data in a performant way, display the submitted data and results visually, and display an up-to-date scoreboard. It also requires the assembly of a back-end service that maintains the score data and potentially supports user registration and login.

Possible technologies that may be useful include:
* [Firebase](https://firebase.google.com/) and/or [Frame](https://jedireza.github.io/frame/)
* [Foundation](http://foundation.zurb.com/), [Semantic UI](https://semantic-ui.com/), [Bootstrap UI](http://www.bootstrap-ui.com/), and/or [Angular](https://angular.io/)
* [SheetJS](http://sheetjs.com/) and/or [Clusterize.js](https://clusterize.js.org/)
* [Leaflet](http://leafletjs.com/)

Non-functional requirements (brainstorm):
* Logging
  * Traffic to the website
  * Submissions
  * Performance on the client side
* Storage
  * Solutions might be somewhat large (could be compressed client-side)
  * Temporary storage for submissions still under evaluation (and may only choose to keep valid solutions or the best ones)
* Configuration
  * Could this be reused for other cities or for other contests
* Performance
  * Evaluation on the client side
  * Transferring data
  * Browser compatibility issues
  * Retrieving solutions
  * Visualizing the solution
* Cost
  * Storage and bandwidth
* Interoperability: does it need to work with other services or frameworks
  * Mapping API
  * Third-party storage service
  * What environment will this operate in?
* Flexibility
  * Could this be reused for other application domains or scenarios
* Accessibility
  * Public website, so maybe it should follow some guidelines or conform to some standards
* Security
  * DDOS?
  * Verify that users are humans
  * Registration to upload
  * Limit submission rate
  * Should solutions be encrypted?
* Disaster recovery
  * Backup the data and user accounts

## Computerized Adaptive Testing Platform

*Credits*: Mary Slavin (Research Assistant Professor of Health Law, Policy & Management, BU School of Public Health)

Computerized adaptive testing (CAT) is a form of computer-based evaluation of individuals (such as patients in recovery) that adapts to the examinee's ability level. This project involves constructing a web-based computerized adaptive testing platform that allows patients to register, self-administer tests, and view their progress. Front-end requirements include accessibility for patient users (e.g., compliance with [Section 508](https://www.section508.gov/)). Back-end requirements include HIPAA compliance.

Possible technologies that may be useful include:
* [Aqua](https://jedireza.github.io/aqua/) or [Frame](https://jedireza.github.io/frame/) (or [Anchor](https://github.com/hicsail/anchor), a BU fork of Frame)
* [Foundation](http://foundation.zurb.com/), [Semantic UI](https://semantic-ui.com/), [Bootstrap UI](http://www.bootstrap-ui.com/), [React](https://facebook.github.io/react/), and/or [Angular](https://angular.io/)
* [Chart.js](http://www.chartjs.org/) or [D3.js](https://d3js.org/)
* [Assets](https://assets.cms.gov/resources/framework/2.0/Pages/) or [Web Experience Toolkit](http://wet-boew.github.io/wet-boew/index-en.html) for accessibility standards compliance

## Mobile App for Traumatic Brain Injury Assessment

*Credits*: Anna Hohler (Associate Professor of Neurology, BU School of Medicine)

Every year roughly 1.7 million Americans sustain a traumatic brain injury, approximately 75% of which are classified as concussions or mild TBI. The goal of this project would be the creation of a cross-platform mobile application that acts as an engaging way to collect preliminary assessment data of the head trauma in order to make a recommendation about the necessity for seeking medical care. The app's front-end may require interactive and real-time features (such as timing or free-form drawing) in order to accommodate the particular measurements that must be made to perform an assessment. The app's back-end would need to support user registration and login and data storage.

Possible technologies that may be useful include:
* [Ionic](https://ionicframework.com/)
* [Aqua](https://jedireza.github.io/aqua/) or [Frame](https://jedireza.github.io/frame/) (or [Anchor](https://github.com/hicsail/anchor), a BU fork of Frame)
* [Chart.js](http://www.chartjs.org/)

Non-functional requirements (brainstorm):
* Logging
  * Every page view
* Storage
  * User accounts, user assessment results
* Configuration
  * Is the backend something that can be deployed within different institutions (or just one big cloud service)
* Performance
  * Timed questions
* Cost
  * Storage
  * Development
  * Time
  * Insurance/liability, terms of use, etc.
* Interoperability: does it need to work with other services or frameworks
  * Integration with third-party medical records/data service (RedCap or any EPIC infrastructure)
* Flexibility
  * Is the backend something that can be deployed within different institutions (or just one big cloud service)
  * Is this primarily for users to self-assess or primarily for a clinical setting
* Accessibility
  * Is the target audience likely to require accessibility features?
* Security
  * Are users comfortable registering with identifying information
  * Is this going to be used in a clinical setting (HIPAA) or a research study (IRB)
* Disaster recovery
  * Users: Store locally or on server? Most likely on server.
  * Service provider: Depends on whether backend service is self-hosted or on the cloud
