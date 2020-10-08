# README

- `demo`: actual used code
  - `run.sh`: build and testscript
    - build: take all (SHACL) shapes
    - workflow:
      - from data you have to reach a goal: forward reasoning
        - till goal is reached or limit is reached
      - preselection: you first give all the reachable rules back by backwards reasoning
  - `index.json`: NO LONGER EXISTS (Is only relevant for the Node.js server, we keep only the version over there)
  - `choices`: files of selected step: is this needed in the server
  - `interim`: is generated by process
    - `subgoals`: if you create a subpath, it could be you don't have data yet to start the subpath
      - createdGoal: creates subgoal
      - extraRule: to create dummy data to find out which input data you need
      - block: it does not apply steps that would create the same data (eg name is added in step 1, don't ask again in step 3)

DISSECT SBO deliverables: have descriptions about gps4ic

noPermutations: makes sure you don't do any step twice, disable permutations

## Files

|   run.*: testing script
|
+---demo
|   |   api-test.sh: api test script
|   |   out.txt
|   |   tree.log
|   |
|   +---apps
|   |       app.handlebars
|   |       index.json
|   |
|   +---choices
|   |       selected_AdditionalData.n3
|   |       selected_AddressChangeInOffice.n3
|   |       selected_AddressSubmission.n3
|   |       selected_BirthData.n3
|   |       selected_CitizenName.n3
|   |       selected_ContactData.n3
|   |       selected_GreenWaste.n3
|   |       selected_GreyWaste.n3
|   |       selected_MovingData.n3
|   |       selected_PaperWaste.n3
|   |       selected_PersonalInfo.n3
|   |       selected_Policevisit.n3
|   |       selected_SubmitWasteInfo.n3
|   |       selected_Waste.n3
|   |
|   +---external-input
|   |       CreateInputPattern.n3
|   |       CreateInputTriple.n3
|   |       example.n3
|   |       example2.n3
|   |       makeTriples.n3
|   |       replaceValue.n3
|   |
|   +---help-functions
|   |       aux2.n3
|   |       built-in-check.n3
|   |       built-ins.n3
|   |       replace.n3
|   |
|   +---interim
|   |   +---input
|   |   |       input_patterns.n3
|   |   |       input_triples.n3
|   |   |       input_triples2.n3
|   |   |       newData.n3
|   |   |
|   |   +---paths
|   |   |       AdditionalData_noPermutation.n3
|   |   |       AddressChangeInOffice_noPermutation.n3
|   |   |       all_journey-paths.n3
|   |   |       BirthData_noPermutation.n3
|   |   |       ChangeAddress_noPermutation.n3
|   |   |       CitizenName_noPermutation.n3
|   |   |       ContactData_noPermutation.n3
|   |   |       GreenWaste_noPermutation.n3
|   |   |       GreyWaste_noPermutation.n3
|   |   |       journey-paths_noPermutations.n3
|   |   |       MovingData_noPermutation.n3
|   |   |       PaperWaste_noPermutation.n3
|   |   |       PersonalInfo_noPermutation.n3
|   |   |       Policevisit_noPermutation.n3
|   |   |       SubmitWasteInfo_noPermutation.n3
|   |   |       WasteContainer_noPermutation.n3
|   |   |
|   |   +---show
|   |   |       query-patterns.n3
|   |   |       show-address-Info.n3
|   |   |       show-address-Info2.n3
|   |   |       show-lastName-Info.n3
|   |   |       show-waste-Info.n3
|   |   |       show-waste-Info2.n3
|   |   |
|   |   +---steps
|   |   |       component-level-steps.n3: output of preprocessing: all component level steps in GPS #1.3
|   |   |       container-level-steps.n3: output of preprocessing: all container level steps in GPS #1.2
|   |   |       GreyWaste_noPermutation.n3
|   |   |       journey-level-steps.n3: output of preprocessing: all journey level steps in GPS #1.1, 2.0-1
|   |   |       selectedSteps_additionalData.n3
|   |   |       selectedSteps_addresschange.n3
|   |   |       selectedSteps_addressChangeInOffice.n3
|   |   |       selectedSteps_birthData.n3
|   |   |       selectedSteps_citizenName.n3
|   |   |       selectedSteps_contactData.n3
|   |   |       selectedSteps_greenWaste.n3
|   |   |       selectedSteps_greyWaste.n3
|   |   |       selectedSteps_Journey.n3: all preselected steps #2.1
|   |   |       selectedSteps_movingData.n3
|   |   |       selectedSteps_paperWaste.n3
|   |   |       SelectedSteps_personalInfo.n3
|   |   |       selectedSteps_policevisit.n3
|   |   |       selectedSteps_submitWasteInfo.n3
|   |   |       selectedSteps_waste.n3
|   |   |       shortComponentDescriptions.n3
|   |   |       shortContainerDescriptions.n3
|   |   |       shortJourneyDescriptions.n3 #2.0-1
|   |   |
|   |   \---subgoals
|   |           block_additionalData.n3
|   |           block_addresschange.n3
|   |           block_addressChangeInOffice.n3
|   |           block_birthData.n3
|   |           block_citizenName.n3
|   |           block_contactData.n3
|   |           block_greenWaste.n3
|   |           block_greyWaste.n3
|   |           block_movingData.n3
|   |           block_paperWaste.n3
|   |           block_personalInfo.n3
|   |           block_police.n3
|   |           block_submitWasteInfo.n3
|   |           block_waste.n3
|   |           createdGoal_additionalData.n3
|   |           createdGoal_address.n3
|   |           createdGoal_addressChangeInOffice.n3
|   |           createdGoal_birthData.n3
|   |           createdGoal_citizenName.n3
|   |           createdGoal_contactData.n3
|   |           createdGoal_greenWaste.n3
|   |           createdGoal_greyWaste.n3
|   |           createdGoal_movingData.n3
|   |           createdGoal_paperWaste.n3
|   |           createdGoal_PersonalInfo.n3
|   |           createdGoal_police.n3
|   |           createdGoal_submitWasteInfo.n3
|   |           createdGoal_Waste.n3
|   |           extraRule_additionalData.n3
|   |           extraRule_addresschange.n3
|   |           extraRule_addressChangeInOffice.n3
|   |           extraRule_birthData.n3
|   |           extraRule_citizenName.n3
|   |           extraRule_contactData.n3
|   |           extraRule_greenWaste.n3
|   |           extraRule_greyWaste.n3
|   |           extraRule_movingData.n3
|   |           extraRule_paperWaste.n3
|   |           extraRule_personalInfo.n3
|   |           extraRule_police.n3
|   |           extraRule_submitWasteInfo.n3
|   |           extraRule_waste.n3
|   |           goal_personalInformation.n3
|   |           Goal_provideMovingData.n3
|   |
|   +---journey
|   |       journeyGoal.n3: #2.1: the endgoal of the algorithm
|   |
|   +---oslo-descriptions: the descriptions of the algorithm/process
|   |       change-address-shapes.ttl: the shapes of the different data elements #1.1-3
|   |       change-address-states.ttl: the states, i.e., basically the label of a data element #1.1-3
|   |       change-address-steps.ttl: the steps: how data flows from input to output per step #1.1-3
|   |
|   +---preselection
|   |       pregeneration.n3: creates :ShortDescription and :reliesOn based on GPS rules #2.0
|   |       prequery.n3: : only keep the actions/input that helps to go to the endgoal #2.1
|   |       preselection.n3: checks which input is needed to reach the endgoal #2.1
|   |
|   +---profile
|   |       knowledge.n3: #2.0-1 business rules
|   |       personalInfo.n3
|   |
|   +---show
|   |       getInfo.n3
|   |       getInput.n3
|   |       out.n3
|   |       query_generation.n3
|   |       query_Info.n3
|   |       query_InfoUsed.n3
|   |       query_used.n3
|   |       Request_showInfoUsed_changeAddress.n3
|   |       Request_showInfoUsed_lastName.n3
|   |       Request_showInfoUsed_personalInformation.n3
|   |       Request_showInfoUsed_wasteCollection.n3
|   |       show-waste-Info.n3
|   |       smallTest.n3
|   |       testquery.n3
|   |       test_show-waste-Info.n3
|   |       waste-info.n3
|   |
|   +---subgoals
|   |       creationOfBlockingInfo.n3
|   |       creationOfRuleForMissingData.n3
|   |       subgoalCreation.n3
|   |       subpath.n3
|   |
|   +---testData
|   |       journey-paths_noPermutations.n3
|   |       personalInfo_testCase.n3
|   |
|   +---translation
|   |       createPattern.n3: UTIL: create `:pattern` structure from SHACL, needed as input for generating the GPS4IC execution rules #1.1-3
|   |       createStatePattern.n3
|   |       help.n3: UTIL: used for :separate function when generating the correct GPS4IC execution rules #1.1-3
|   |       mappingRuleCreationComponent.n3: generate GPS descriptions with weights for components #1.2
|   |       mappingRuleCreationContainer.n3: generate GPS descriptions with weights for containers #1.1
|   |       mappingRuleCreationJourney.n3: generate GPS descriptions with weights for journeys #1.3
|   |       statePatternCreation.n3
|   |       step-reasoning.n3: UTIL: each type of step is also just a step. #TODO Can this be removed? needed as input for generating the GPS4IC execution rules? #1.1-3
|   |
|   \---workflow-composer
|           gps-plugin.n3
|           gps-plugin_modified.n3
|           gps-plugin_modified_noPermutations.n3
|
+---ld-generation
|       download-mapper.sh
|       download-sheets.sh
|       fast-data.ttl
|       map.sh
|       mapping.yml
|       Shapes-Constraints.csv
|       Shapes.csv
|       States-Shapes.csv
|       States.csv
|       Steps-Descriptions.csv
|       Steps.csv
|
+---Preselection
|       gps-example2.n3
|       gps-example22.n3
|       gps-plugin.n3
|       gps-proof2.n3
|       gps-query2.n3
|       gps-query3.n3
|       gps-query4.n3
|       out.n3
|       out2.n3
|       pgquery.n3
|       plugin.n3
|       pregeneration.n3
|       pregeneration2.n3
|       prequery.n3
|       preselection.n3
|       preselection2.n3
|       shortdescriptions.n3
|       shortdescriptions2.n3
|
+---test
|       in.n3
|       out.n3
|       query.n3
|
\---tmp
    \---demo
        \---interim
            +---paths
            \---steps

## TODO

- [ ] What is :pattern?
  - input: stateShape
  - output: list of 4 elements
    - 1. triples graph with the path
    - 2. graph where the path graph is skolemed to the output
    - 3. output: deprecated?
    - 4. ???
- [ ] What does the :separate function do?
- [ ] What does the :unfold function do?
- [ ] What does e:skolem do?
- [ ] :ShortDescription and :reliesOn?
