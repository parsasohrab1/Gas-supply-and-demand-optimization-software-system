# Gas-supply-and-demand-optimization-software-system
Documentation of the National Gas Supply and Demand Optimizer Software System
(Software Requirements Specification - SRS)
1. Scope
This software system is designed to integrate, analyze and optimize natural gas supply and demand across the country's national grid. The primary user is the National Gas Dispatching Planning Affairs, which is responsible for preparing the country's annual gas balance plan.

2. Reference Documents
Project questionnaire "Gas Supply and Demand Optimizer Software" – Petro Palatos Knowledge-Based Company

Fee instruction for specialized research service agents – Research and Technology Management of the National Iranian Gas Company

3. General System Requirements
3-1. Overall Objective
Design and implement integrated software based on mathematical models and optimization algorithms to establish a stable balance between the country's gas supply and demand with minimum imbalance and the lowest consumption of liquid products in power plants.

3-2. High-Level Objectives
Objective 1 (Balance): Achieve an accurate balance of gas supply and demand with an error of less than 5 percent

Objective 2 (Liquid fuel reduction): At least a 10 percent reduction in fuel oil and gas oil consumption in power plants

Objective 3 (Speed): At least a 50 percent reduction in the time to prepare the annual plan compared with the Excel-based method

Objective 4 (Forecast accuracy): Achieve accuracy above 90 percent in forecasting network status

3-3. System Users
Primary users: Experts of the National Gas Dispatching Planning Affairs

Secondary users: Planning and strategy managers of the National Iranian Gas Company, refinery and power plant experts

System administrators: Technical software support and maintenance team

3-4. General Constraints
Full compliance with the structure of the country's gas network and domestic regulations

Ability to integrate with existing databases at the National Iranian Gas Company

Compliance with national-level cybersecurity standards

Ability to be installed and run on existing hardware infrastructure

4. Review of Similar Patents and Determination of Technical Differentiation
4-1. Review of Existing Patents and Systems
1. Smart grid gas supply deployment method and Internet of Things system (US 20240311936 A1)

This patent, filed by a Chinese company, focuses on controlling gas metering devices in target areas, forecasting future demand based on historical consumption data, and determining the range of the supply-demand difference. Using machine learning models, the system identifies the cause of the supply-demand difference and suggests gas supply adjustment parameters.

Key limitations:

It focuses solely on the regional level (target area) and has no planning capability at the national network level.

It lacks simultaneous integration of key variables such as the turnaround schedule of refineries and transmission lines.

The main goal is responding to imbalance in real time, and it does not cover long-term strategic planning.

2. Intelligent decision-making method and operational planning software for natural gas pipelines (NGPOS-IDMS)

This research, published in the Journal of Pipeline Systems Engineering and Practice, presents a combination of a database-driven decision method (DMD) and an optimization-algorithm-based method (DMOA) for a pipeline network and proposes six decision-making modes based on fuzzy database query technology.

Key limitations:

It focuses on a gas pipeline network at the scale of one company or one specific corridor, not the entire national supply chain.

The optimization models presented for deterministic and uncertain supply scenarios do not simultaneously consider turnarounds and power plant fuel consumption.

3. Gas system balancing and optimal planning method, device and system (CN101794119A)

This registered Chinese patent from 2010 relates to a gas balancing and optimal planning system in petrochemical companies that, based on forecast data, predicts the gas production of each production unit and the energy demand of heating furnaces in a given period and, in case of imbalance, provides the optimal strategy and schedule.

Key limitations:

Designed at the level of a single petrochemical company and not the national gas network, which is far larger and more complex.

It focuses on associated gases and by-products of oil refineries, not the natural gas of the national grid.

4. Dynamic optimization model of the European gas network distribution and investment (GNOME)

The GNOME model, introduced in Operations Research Forum, is a high-resolution dynamic mixed-integer linear programming (MILP) model for the European gas network and its external suppliers. This model meets each country's gas demand with a low-cost combination of domestic production, pipeline flow, LNG imports and use of storage.

Key limitations:

It mainly focuses on trade flows and infrastructure investment, not daily/seasonal operational optimization and reducing liquid fuel consumption in power plants.

It lacks the ability to integrate with the equipment turnaround schedule at the operational level.

5. Patents related to gas pool balancing (Williams Gas Pipeline - US7587326B1)

This patent, assigned to Williams Gas Pipeline Company, provides a method for simultaneous and systematic balancing of the entire gas transmission network by identifying gas "pools", numerically distributing gas in the network and then physically distributing it based on the obtained solutions.

Key limitations:

It focuses on flow balancing in the (refinery) pipeline network and does not cover the entire supply chain (production, storage, export, power plants).

It is designed mainly for real-time or short-term operations and lacks annual strategic planning capability.

4-2. Technical Differentiation of the Proposed Invention
Key feature	Similar patents	Proposed invention (differentiation)
Network scale	Regional, petrochemical, specific pipeline	The national gas network with all components of the supply chain (refineries, transmission, storage, export/import, power plants, industries and household consumption)
Turnaround integration	Mainly not considered or only limited	Complete integration of the turnaround schedule of refineries, transmission lines and key equipment in the optimization model
Multi-dimensional objective function	Mainly cost minimization or welfare maximization	Combined objective function: (1) minimizing gas imbalance, (2) minimizing liquid fuel consumption (fuel oil and gas oil) in power plants, (3) minimizing operating costs
Solution approach	Linear programming, MILP, or simple heuristics	Hybrid metaheuristic algorithms (a combination of genetic algorithms, particle swarm and ant colony optimization) with high scalability
Intelligent forecasting	Mainly based on simple historical data	Deep-learning-based forecasting models (LSTM, GRU) for forecasting seasonal consumption and the effects of weather conditions
Scenario analysis	Usually limited to a few predefined scenarios	Dynamic generation and analysis of hundreds of different scenarios (optimistic, pessimistic and probable) with intelligent reporting
Excel replacement	Specialized systems with closed architecture	Complete replacement of the manual Excel-based method with an integrated and user-friendly decision support system
Localization	Generally based on the conditions of other countries	Designed based on the specific structure of Iran's gas network, operational constraints, and domestic laws and regulations
5. Functional Requirements
5-1. Data Management
ID	Requirement	Priority
FR-01	The system must be able to receive, store and integrate gas production data from all refineries in the country	Essential
FR-02	The system must be able to receive and store gas consumption data in the household, industry, power plant and petrochemical sectors	Essential
FR-03	The system must be able to record, update and manage the turnaround schedule of all production units and transmission lines	Essential
FR-04	The system must be able to record gas export and import data (volume, price, schedule)	Essential
FR-05	The system must be able to validate input data for accuracy, completeness and consistency	Essential
FR-06	The system must be able to store different versions of data and generated plans	Desirable
5-2. Mathematical Modeling
ID	Requirement	Priority
FR-07	The system must have a complete mathematical model of the country's gas network with definition of production, consumption, storage and transmission nodes	Essential
FR-08	The system must be able to define an objective function with weighting capability for different criteria (imbalance, liquid fuel consumption, cost)	Essential
FR-09	The system must model all operational constraints (line capacity, pressure, gas quality, storage constraints)	Essential
FR-10	The system must be able to model uncertainties (seasonal consumption changes, equipment failure, price changes)	Important
FR-11	The system must be able to apply different policy scenarios (changing export ceilings, consumption restrictions, changing energy carrier prices)	Important
5-3. Optimization and Forecasting Algorithms
ID	Requirement	Priority
FR-12	The system must implement at least one metaheuristic algorithm (genetic algorithm, particle swarm or a hybrid) to solve the optimization problem	Essential
FR-13	The system must implement a deep-learning-based gas consumption forecasting model (LSTM or equivalent)	Essential
FR-14	The system must be able to perform sensitivity analysis on key parameters	Important
FR-15	The system must be able to simulate and compare different optimization scenarios	Essential
FR-16	The algorithm must be able to produce the optimal solution in a reasonable time (at most 60 minutes for an annual plan)	Essential
5-4. User Interface and Reporting
ID	Requirement	Priority
FR-17	The system must have a management dashboard showing the overall network status (production, consumption, imbalance, storage)	Essential
FR-18	The system must be able to generate various analytical reports (balance report, fuel consumption report, turnaround report, scenario report)	Essential
FR-19	The system must be able to graphically display the gas network and node status	Important
FR-20	The system must be able to export in standard formats (Excel, PDF, CSV)	Essential
FR-21	The system must support user access level management (admin, senior expert, expert, viewer)	Essential
5-5. Integration
ID	Requirement	Priority
FR-22	The system must be able to receive data through web services (API) from existing systems of the National Iranian Gas Company	Essential
FR-23	The system must be able to connect to enterprise databases (Oracle, SQL Server)	Essential
FR-24	The system must be able to exchange data with refinery and power plant systems	Important
6. Non-Functional Requirements
6-1. Performance and Scalability
ID	Requirement	Target value
NFR-01	Response time for displaying the dashboard	Less than 3 seconds
NFR-02	Execution time of the optimization algorithm for the annual plan	Less than 60 minutes
NFR-03	Historical data retrieval time	Less than 10 seconds per year
NFR-04	Maximum number of concurrent users	At least 50 users
NFR-05	Data storage capacity	At least 10 years of operational data
6-2. Security and Reliability
ID	Requirement	Description
NFR-06	Two-factor authentication	For users with high-level access
NFR-07	Data encryption	Sensitive data must be encrypted with AES-256
NFR-08	Automatic backup	Daily database backup
NFR-09	Event logging (Audit Log)	Logging of all user activities and changes
NFR-10	System availability	At least 99% during working hours
6-3. Usability
ID	Requirement	Description
NFR-11	User interface language	Persian with support for Solar Hijri numbers and dates
NFR-12	User documentation	Complete user guide in Persian
NFR-13	User training	In-person and online training courses for primary users
NFR-14	In-app guidance	Tooltips and step-by-step guidance within the software
6-4. Maintainability
ID	Requirement	Description
NFR-15	Modular architecture	Ability to develop and update modules independently
NFR-16	Technical documentation	Complete documentation of the architecture, database and coding
NFR-17	Troubleshooting capability	Comprehensive logs for troubleshooting and error resolution
7. Use Cases
Main scenario: Preparing the annual gas balance plan
The expert enters new production, consumption, turnaround, export and import data into the system

The system validates the data and issues a warning if there is an error

The expert sets the optimization parameters (objective function weights, constraints)

The system runs the optimization algorithm with the entered data

The system displays the optimal production and consumption plan along with an analytical report and charts

The expert reviews the plan and, if necessary, runs alternative scenarios

The final plan is issued together with documentation for final approval

Forecasting and alerting scenario
The system automatically receives real-time data from production and consumption sources

The forecasting model simulates the network status for the next 7 days

If a critical imbalance is predicted, an alert is sent to the expert

The expert reviews the system's proposed scenarios for crisis management

Turnaround analysis scenario
The annual turnaround schedule is recorded through an API or manual entry

The system simulates the effects of each unit's turnaround on the overall network balance

The expert observes the effect of turnarounds on liquid fuel consumption in different scenarios

8. Overall System Architecture
Architecture Layers
Presentation Layer: Web-based user interface (React/Vue.js) with interactive dashboards

Application Layer: API Gateway, optimization services, forecasting services, data management service

Data Layer: Relational database (PostgreSQL) and time-series database (InfluxDB or TimescaleDB)

Infrastructure Layer: Virtual servers, cloud storage, backup

Main Components
Optimization engine: Implementation of metaheuristic algorithms using Python and the NumPy and SciPy libraries

Forecasting engine: LSTM models using TensorFlow/Keras

Data management: ETL Pipeline for integrating data from different sources

Management dashboard: Display of network status, reports, and interactive analyses

9. Design Constraints
ID	Constraint	Description
DC-01	Use of open-source software	Preference for Open Source software to reduce costs
DC-02	Compliance with National Iranian Gas Company standards	Full compliance with the ICT standards of the National Iranian Gas Company
DC-03	Ability to run on existing hardware	Designed based on the existing servers of the National Iranian Gas Company
DC-04	Operating-system independent	Ability to be installed on Linux and Windows Server
10. Assumptions and Dependencies
Assumptions
The required data can be provided through cooperation of the National Iranian Gas Company, refineries and power plants

The required network and hardware infrastructure is available at the National Iranian Gas Company

Users have sufficient knowledge of gas network planning

Metaheuristic algorithms can provide an acceptable solution to the problem in a reasonable time

Dependencies
Cooperation of various organizations to provide up-to-date and accurate data

Approval of the Research and Technology Organization of the National Iranian Gas Company

Providing required software licenses (if needed)

11. Appendices
Appendix 1: Conceptual data model
Refineries table

Transmission lines table

Consumption nodes table

Storage facilities table

Turnarounds table

Scenarios table

Optimization results table

Appendix 2: Proposed algorithms
Main optimization algorithm: Genetic algorithm with custom combination operators tailored to the gas balancing problem

Consumption forecasting algorithm: LSTM network with 3 hidden layers

Turnaround optimization algorithm: Particle swarm algorithm with time constraints

Appendix 3: Key evaluation indicators (KPIs)
Indicator	Measurement method	Target value
Balance accuracy	Mean absolute percentage error (MAPE)	< 5%
Liquid fuel reduction	Comparison with the manual plan	≥ 10%
Plan preparation time	Time from data entry to final output	≤ 60 minutes
Forecast accuracy	RMSE	≤ 5%
User satisfaction	User survey	≥ 80%
12. Approval Signatures
Role	Name	Signature	Date
Project manager	Nosratali Ashrafi Payaman
Main collaborator	Mohammad Parsa Sohrabi
Main collaborator	Elham Kokabi Dana
Main collaborator	Mansoureh Ghorbani
Main collaborator	Bahareh Kordi
Main collaborator	Elham Bideh
Main collaborator	Rostam Ghasemkhani
