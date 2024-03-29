# Exsys's CurePlus Docs

![cureplus logo](https://user-images.githubusercontent.com/12882714/108598469-7929c000-7396-11eb-94a3-5fd9911774b8.png)
 
 
 ### in this file you will find the following.

- Clone Repo and install typescript
- App Structure
- How we use Git
- Create new package
- How to: Package Structure (screen)
- How to: Create Page Labels
- How to: Hooks (useBasicQuery, useBasicMutation,useCodeQuery)
- Build (cloud)
- Build (update env )
- Genrate Route
- Exsys Components
- Antd 3 v ^3.19.3
- adding third party packages
- more on MONO REPO

## Clone Repo

- visit (https://bitbucket.org/anspire/ex-webapp/src/master/)
- login and click on Clone
- open vscode and open terminal 

```sh
  git clone git@bitbucket.org:anspire/ex-webapp.git
```
- After clone is done installing all packages and deps required for running the app
- please run the following command  at the very root of the project.
-- please make sure u have lerna and typescript installed globally before running the following command
```sh 
yarn add global lerna
yarn add global typescript
```
- see the lerna-add repo docs https://github.com/lerna/lerna/tree/master/commands/add
```sh 
yarn bootstrap
```

## App structure 

```sh 
├─> app #  Javascript Redux saga  (old structure )   
 │   ├── .env   #global enviorment variables
 │   ├─> public
 │   └─> src
 │   │   ├─> globals
 │   │   │   ├─> actions
 │   │   │   ├─> reducers #inject page redcures
 │   │   │   ├─> sagas #inject page sagas
 │   │   │   └─> types
 │   │   ├─> Hocs
 │   │   │   ├─> createInput
 │   │   │   ├─> PriviligiesChecker
 │   │   │   ├─> TableHoc
 │   │   │   ├─> TreeHoc
 │   │   │   └─> withPagination
 │   │   ├─> infrastructure
 │   │   │   └─> Pagination
 │   │   ├─> Pages # App pages
 │   │   │   ├─> AdmissionFinancialBalance
 │   │   │   ├─> BinLocations
 │   │   │   ├─> CancelEpisodeInvoice
 │   │   │   ├─> CancelStatement
 │   │   │   ├─> CashierDesktop
 │   │   │   ├─> ClinicalEntities
 │   │   │   ├─> ClinicalSpecialities
 │   │   │   ├─> CreateDhsDraft
 │   │   │   ├─> CreateEpisodeInvoice
 │   │   │   ├─> CreateStatement
 │   │   │   ├─> CreditPatientInvoiceSummary
 │   │   │   ├─> CustomerStatmentQuery
 │   │   │   ├─> Dashboard
 │   │   │   ├─> DentalDesktop
 │   │   │   ├─> DoctorDesktop
 │   │   │   ├─> DoctorServicesVolume
 │   │   │   ├─> DosageCodes
 │   │   │   ├─> Eligibity
 │   │   │   ├─> EmergencyDesktop
 │   │   │   ├─> ExcelUpload
 │   │   │   ├─> ExPage
 │   │   │   ├─> ExsysApis
 │   │   │   ├─> ExternalDoctor
 │   │   │   ├─> FinancialYear
 │   │   │   ├─> GeneralDesktop
 │   │   │   ├─> InventoryGroup
 │   │   │   ├─> InvestCategory
 │   │   │   ├─> LabelsPage
 │   │   │   ├─> MiApprovalQuery
 │   │   │   ├─> MiBatchQuery
 │   │   │   ├─> Mimedaprvl
 │   │   │   ├─> miPatientIssue
 │   │   │   ├─> Misrvaprvl
 │   │   │   ├─> MiTicketQuery
 │   │   │   ├─> Miucafaprvl
 │   │   │   ├─> ModuleClientCodes
 │   │   │   ├─> ModuleCodes
 │   │   │   ├─> ModulePeriods
 │   │   │   ├─> MrdReview
 │   │   │   ├─> NursingDesktop
 │   │   │   ├─> OphthalmolgySetup
 │   │   │   ├─> OpthDesktop
 │   │   │   ├─> OpthNurseingDetails
 │   │   │   ├─> OpthScreening
 │   │   │   ├─> OutpatientGiInterface
 │   │   │   ├─> OutpatientOperations
 │   │   │   ├─> OutpatientOperationsNew
 │   │   │   ├─> PaitentBillingAudit
 │   │   │   ├─> PatientAdmission
 │   │   │   ├─> PatientBillingInvoiceQuery
 │   │   │   ├─> PatientDonation
 │   │   │   ├─> PatientIssue
 │   │   │   ├─> PatientLetters
 │   │   │   ├─> PatientReading
 │   │   │   ├─> PatientRequestApproval
 │   │   │   ├─> PaymentCode
 │   │   │   ├─> PbmrPrinting
 │   │   │   ├─> RcActivityQuery
 │   │   │   ├─> ReceptionInvoiceQuery
 │   │   │   ├─> ServiceDoctorCount
 │   │   │   ├─> SiteInformation
 │   │   │   ├─> StaffDepartment
 │   │   │   ├─> StaffMaster
 │   │   │   └─> XrayExamDefinitions
 │   │   ├─> routes #do not update manually 
 │   │   └─> utlities
 │   │       ├─> AWSUploader
 │   │       └─> generators
 │   │       │   ├─> injector
 │   │       │   └─> treePage
 ├─> packages # Typescript + Context Structure (new structure)
 │   ├─> app-footer
 │   ├─> base-page
 │   ├─> cash-shift-context
 │   ├─> clinical-speciality-page
 │   ├─> colors #main app colors 📦
 │   ├─> commons
 │   │   └─> src
 │   │   │   ├─> BorderedContainer
 │   │   │   ├─> FieldShadowWrapper
 │   │   │   ├─> Flex
 │   │   │   ├─> IconContainer
 │   │   │   ├─> Loadable
 │   │   │   ├─> Text
 │   │   │   ├─> TextContainer
 │   │   │   └─> TwoSectionsPage
 │   ├─> customize-webpack
 │   ├─> desktop-header
 │   ├─> environment # global enviorment  urls (like base url)📦
 │   ├─> form-manager # form manager (handle change, clears form, validate form)
 │   ├─> form-ui # Common UI  input controls   📦
 │   │   └─> src
 │   │   │   ├─> Checkbox
 │   │   │   ├─> Date
 │   │   │   ├─> InlineLabelInput
 │   │   │   ├─> Input
 │   │   │   ├─> Radio
 │   │   │   ├─> Select
 │   │   │   └─> Switch
 │   ├─> generators
 │   ├─> home-page
 │   ├─> icon
 │   ├─> image
 │   ├─> images
 │   ├─> input-with-shadow
 │   ├─> jsx-icons  #Common  APP Icons📦
 │   ├─> labels-cache-manager #local storage for cached labels📦
 │   ├─> labels-provider  #labels for all app 📦
 │   ├─> loader-fallback
 │   ├─> local-storage
 │   ├─> login-page
 │   ├─> mi-batch-claim
 │   ├─> mi-batchs-page
 │   ├─> mi-claim-invoices
 │   ├─> modal
 │   ├─> popup-list-with-search
 │   ├─> rcm-billing-items-page
 │   ├─> rcm-insurance-companies-page
 │   ├─> rcm-rejection-reasons-page
 │   ├─> rcm-validat-dhs-page
 │   ├─> react-lazy
 │   ├─> refetch
 │   ├─> routes
 │   ├─> table #table 📦 (base table, table with header)
 │   ├─> types
 │   └─> validators 
```
## How we use Git 
> instead of creating Pull request, we rebase from master.
>@see https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase#:~:text=Rebase%20is%20one%20of%20two,has%20powerful%20history%20rewriting%20features.
1) When creating a new branch from master:
	```sh 
	git checkout -b my_awesome_branch
	git fetch origin (to update your local repo)
	```
2) After making changes to my_awesome_branch:- 
	```sh 
	git add .
	git commit -m "commit message"
	git push origin my_awesome_branch
 	```	
> NOW Update your branch with master FIRST!
 
	git fetch origin
	git rebase origin/master 
>(to rebase what's on the master to my_awesome_branch, thus making the changes in the master available in my_awesome_branch, and if conflicts arises, reslove them)

 >If conflicts arises, reslove them then
 
	git add.
	git rebase --continue
	ctrl+c
	:qa

> We need to update the remote my_awesome_branch with the rebased local my_awesome_branch, in order to achieve this do the following:

	git add.
	git commit -m "your message"
	git push origin my_awesome_branch -f
	:qa

> (We use force because the remote branch doesn't have the rebased local branch)

	***** WHEN YOU NEED TO REBASE YOUR WORK ON MASTER we need to ensure that all your commits are rebased as one commit. In order to achiecve this: 
	- We count the number of your commits from bitbucket, let's assume 3 commits
	- git reset HEAD~3
	- git add .	
	- git commit -m "your message"
	- git push origin my_awesome_branch -f (We use force because the remote branch doesn't have the rebased local branch)

  > 	Now you are good to go to rebase your work on master :)
	- git checkout master
	- git fetch origin
	- git rebase origin/my_awesome_branch
	- git pull --rebase origin master
	- git add .
	- git commit --amend --no-edit
	- git push origin master


3) Before starting to work on your branch, must have the latest work on master

	   git fetch origin
	   git rebase origin/master
 
  > In order to update your local master branch:
   
	   git fetch origin
	   git pull --rebase origin master
	   
 
## Create New Package (screen)
> for this section will be creating page package

open vs code terminal in our project,
>we have generator that will help you to generate package, with code transpiling and routes generation 
you will be asked to choose package type
--react package 
--other package

```
yarn generate
[x]react package (choose this)
[--]other package
```
## if you choose react package, you will be asked to choose again to pick between
```
[--]normal component
[--]lazy-loaded component
[x] page (choose page)
```
## you will be asked to what is the **name** of your package
>we have naming convention all small letter with dash
example  if your page called rcm validate dhs
your package should be named rcm-validate-dhs-**page**
 ## you will be asked to what is the **descirption** of your package
>describe your package in meaningful way
  ## you will be asked to what is the **route path** is
>with coordation  with eng.Nagy, package route path will be provided by him,
by default it will be the package name
   ## you will be asked to what is the **route param(s)**
> if your package do not have any param(s) press enter
if your package have param(s) enter them seperated by comma
example param1,param2

## you will be asked to wrap your component using **styled component**
 > depending if you need to create your own styled component  
 press Y/n  to create/decline
 

## How to: Package Structure
  >by default when generating package the output will be
```
|-- src
        |-- component.tsx **wrapping views from partials with labels provider*
        |-- index.interface.ts # for types and interfaces
        |-- index.ts #wrapping lazy  **component**
        |-- styled.ts
|-- package.json # will discuss next
|-- README.md  #package description
|--tsconfig.json
 
```
> addtionaly you can add the following
```
|-- page-name
    |-- src
        |-- helpers // each file has only 1 function 
            |-- transformData.ts //depends on if you need to transform object into custom model
        |-- partials  # lets assuem we have form and table section
            |-- FormView.ts  
            |-- TableView.ts    
   
```




## How to: useBasicQuery
  >useBasicQuery is used for fetching data from API example 1
 
```JSX
import React, { useCallback, useEffect } from "react";
import { useBasicQuery } from "@app-structure/network-hooks/";
import { PolicyData } from "../index.interface";

const View: React.FC = () => {
  const [policyData, setPolicyData] = useState<PolicyData>();

// u can add alias
   const { runQuery: policyQuery, loading } = useBasicQuery({
    apiId: "POP_POLICY_INFO",
    callOnFirstRender: false, // set to true if you want to be called at first
    onResponse: setPolicyData,
    withLanguageParam: true,//lang params
    params: {
      policy_no: values.policy_no //addtional params
    },
    //@ts-ignore
    transformApiDataFn: (data: { data: PolicyData }) => data?.data[0] // to transform data
  });
  return (<>
                  {JSON.stringify(policyData)}

        </>)
};
export default React.memo(View);
```
 >useBasicQuery is used for fetching data from API example 2
 
```JSX
import React, { useCallback, useEffect } from "react";
import { useBasicQuery } from "@app-structure/network-hooks/";
import { PatientResult } from "../index.interface";

const View: React.FC = () => {
  const [patientData, setPatientData] = React.useState<PatientResult>();

   const onPatientResponse = React.useCallback(data => {
    if (data?.data) {
      const patientInfo = data.data[0] as PatientResult;

      patientInfo && setPatientData(patientInfo);
     
    }
  }, []);
  const { runQuery: patientSearch } = useBasicQuery({
    apiId: "PATIENT_DATA",
    // params:,
    callOnFirstRender: false,
    onResponse: onPatientResponse
  });
  const handleSearchInput = React.useCallback(
    (value: string) => {
      patientSearch({
        request_date: moment().format(DATE_FORMAT),
        search_type: "C",
        search_value: value,
        language_id: planguageid
      });
    },
    [patientSearch, planguageid]
  );
  return (<>
                  {JSON.stringify(patientInfo)}
   <LabelledInput label="Patient Card No" labelFlex={1.32} width="450px">
            <SearchInput
              placeholder="search for patient card no"
              onSearch={handleSearchInput}
              enterButton
            />
  </LabelledInput>

        </>)
};
export default React.memo(View);
```


## How to: useCodeQuery
  >useCodeQuery is used for fetching data from API WITH type code or u_code
 
```JSX
import React, { useCallback, useEffect } from "react";
import { useCodeQuery } from "@app-structure/network-hooks/";
import { SelectListProps } from "@app-structure/types";


const View: React.FC = () => {
  const [medicationTypeList, setMedicationTypeList] = React.useState<SelectListProps[]>([]);
  useCodeQuery({
    type: "u_code",
    codeId: "MEDICATION",
    onResponse: setMedicationTypeList,
    callOnFirstRender: true
  });
  return (<>
                  <Select
                  name="medication_type"
                  value={values.medication_type}
                  onChange={handleChange}
                  options={medicationTypeList}
                  width="100%"
                  size="default"
                />

        </>)
};
export default React.memo(View);
```
  
## How to: useBasicMutation
  >useBasicMutation is used for POST data from API 
 
```JSX
import React, { useCallback, useEffect } from "react";
import { useBasicMutation ,useBasicQuery} from "@app-structure/network-hooks/";


const View: React.FC = () => {

 const { runQuery } = useBasicQuery({
    apiId: "EXCEL_FILE",
    callOnFirstRender: false,
    onResponse: onResponseClaimStatistics,
    params: {
      claim_month: formValues.month
        ? moment(formValues.month).format("MM")
        : "",
      claim_year: formValues.year ? moment(formValues.year).format("YYYY") : "",
      client_id: formValues.clientId,
      medical_insurance_id: formValues.insurance_no,
   
    }
  });
  const { mutate } = useBasicMutation({
    apiId: "UPLOAD_EXCEL_FILE",
    method: "post"
  });
 
 
 const saveData = useCallback( () => {
       mutate({
          body: {
            ...yourObj
            
          },
          //@ts-ignore
          cb: (res: RecordType, err?: string | boolean) => {
            if (!err) {
             
              runQuery();//to rerender API
              notification.success({
                message: "file added successfully "
              });
            } else {
              console.error({ err });
              notification.error({
                message: "Something went wrong"
              });
            }
            
          }

          
        });
  }, [  mutate, runQuery]);

 
  return (<>
                  <Button
                  name="save"
               
                  onClick={saveData}  
                  width="100%"
                  
                />

        </>)
};
export default React.memo(View);
```


## How to: Create Page Labels
>exsys is 2 lanague based system (arabic & english)
>
>to add your labels 
>
>1- run the app ```yarn start``` then login using exysdba/123456
>
>2- navigate to **/labels**
>
>3- in ***table section*** search for your label if its common like ***(date from or date to)*** and select it
>
>4- in ***poge search section*** search for your screen name like ***(rcmDhs)*** and click save
>
>***from table section there're 2 columns, one for labelId and one for label description*** 
>
>5- most of components are wrapped in BaseText after all (labled inputs, date)
>
>example below 

```JSX
import React, { useCallback, useEffect } from "react";
 
import { PageTitle } from "@app-structure/commons/src";
const View: React.FC<TableActionViewProps> = ({
  Id,
  showModal,
  toggleModal
}) => {
   
  return (<>
             <PageTitle
              fontsize="17px"
              children={"revisionandupload"} # just add ur tite in ""
              margin="0"
            />
        </>)
export default React.memo(View);
```



 

## Build (Cloud)

open vs code terminal
```
yarn build
follow the cli questions(normally go for cloud then press enter and so on)
```
 
## Build Update Env
>navigate to environment package
```
|-- packages
	|-- environment
	    |-- src
		 |-- getBuildDates.js 
		 |-- index.js    
	  |-- package.json  
 
```
>open ```index.js```

```Javascript
/*
 *
 * Package: `@app-structure/environment`.
 *
 */
const { year, day, month, time } = require("./getBuildDates");

/** STEPS TO ADD NEW CLIENT */
// 1)- in `CLIENTS_NAMES` variables add the new client.
// 2)- in `CLIENTS_URLS` variables add the new client url.

const CRA_PREFIX = "REACT_APP_";

const BASE_OPTIONS_KEYS_FROM_PKG_JSON = {
  BUILD_YEAR: "BUILD_YEAR",
  BUILD_MONTH: "BUILD_MONTH",
  BUILD_DAY: "BUILD_DAY",
  BUILD_TIME: "BUILD_TIME"
};

// note that these keys values will be prefixed with `REACT_APP_` in the final
// process of this module. like `BASE_URL` will be `REACT_APP_BASE_URL=whatever`
// and you can access it's value like this `process.env.REACT_APP_BASE_URL`.
const ALLOWED_VARIABLES_KEYS_TO_ENV_FILE = {
  ...BASE_OPTIONS_KEYS_FROM_PKG_JSON,
  BASE_URL: "BASE_URL",
  API_URL: "API_URL"
};

const OPTIONS_KEYS_FROM_PKG_JSON = {
  CLIENT: "CLIENT",
  SERVER_PORT: "SERVER_PORT",
  ...BASE_OPTIONS_KEYS_FROM_PKG_JSON
};

const CLIENTS_NAMES = {
  CLOUD: "cloud",
  SAGAF: "sagaf",
  SAGAF_TEST: "sagaftest",
  TADAWY: "tadawy",
  NEWCLIENT:"NEWCLIENT"  //newly added client
};

const DEFAULT_VARS_WITH_VALUES = {
  [OPTIONS_KEYS_FROM_PKG_JSON.SERVER_PORT]: "9090",
  [OPTIONS_KEYS_FROM_PKG_JSON.CLIENT]: CLIENTS_NAMES.CLOUD,
  [OPTIONS_KEYS_FROM_PKG_JSON.BUILD_YEAR]: year,
  [OPTIONS_KEYS_FROM_PKG_JSON.BUILD_MONTH]: month,
  [OPTIONS_KEYS_FROM_PKG_JSON.BUILD_DAY]: day,
  [OPTIONS_KEYS_FROM_PKG_JSON.BUILD_TIME]: time
};

const CLIENTS_URLS = {
  [CLIENTS_NAMES.SAGAF]: "http://192.168.15.15",
  [CLIENTS_NAMES.CLOUD]: "http://161.97.142.25",
  [CLIENTS_NAMES.SAGAF_TEST]: "http://TEST-WEBDB",
  [CLIENTS_NAMES.TADAWY]: "http://192.168.1.100"
  [CLIENTS_NAMES.NEWCLIENT]: "http://192.168.1.985" // NEW client URL
};
module.exports = {
  DEFAULT_VARS_WITH_VALUES,
  CLIENTS_NAMES,
  CLIENTS_URLS,
  OPTIONS_KEYS_FROM_PKG_JSON,
  CRA_PREFIX,
  ALLOWED_VARIABLES_KEYS_TO_ENV_FILE
};


```

#### Genrate Route
>lets assuem ur page route will be changed, or your page will accept param(s)
>
>all you need to update ur package.json like below
>
>then run``` yarn generate-routes```
>
>this command will update routes file in  ```app->routes->pagesRoutesData.ts```
>
>this command can be found ***in root package.json in scripts section***

```Javascript
{
  "name": "@app-structure/demo-page",
  "version": "1.0.0",
  "private": true,
  "description": "demo package.",
  "author": "exsys",
  "license": "ISC",
  "main": "src/",
  "sideEffects": false,
  "dependencies": {
    "@app-structure/labels-provider": "1.0.0"
  },
  "peerDependencies": {
    "@types/react": "^16.x.x",
    "@types/styled-components": "^5.x.x"
  },
  "routeData": {
    "path": "/demo1"  |#page url
    "params": [ |#page param(s)
      "batch_no",
      "batch_date",
      "total_claim?" //optional params
    ]
  },
  "enableBabelTranspilation": true  | #this will be transpilated 
}
 
```
## Exsys Components
### form UI
- contains common UI components like checkbox, radio, select,..etc 
> take a look for each of them
### commons
- contains  BorderedContainer, Flex, IconContainer, ..etc
 > take a look for each of them

### createLazyComponent
- for lazy loading components, common usage for modal
```JSX
import createLazyComponent from "@app-structure/react-lazy";

const Modal = createLazyComponent(() =>
  import("@app-structure/modal" /* webpackChunkName: "app-structure.modal" */)
);

```

## Antd 3 version ^3.19.3
![reactant_vectorized](https://user-images.githubusercontent.com/12882714/108610671-296fe680-73e0-11eb-9e82-b32df9b71b7c.png)

## [please check ant design 3 components ](https://3x.ant.design/docs/react/introduce)
 
# adding third party packges
>to add dev depdencay 
```
lerna add --dev @types/crypto-js  --scope @app-structure/aws-uploader (dev dep
lerna add -dev some package --scope @app-structure/aws-uploader (dep)
```
> to add package shared in all app

```
yarn add classnames --ignore-workspace-root-check

```
## MONOREPO
https://www.toptal.com/front-end/guide-to-monorepos


# videos
https://1drv.ms/u/s!Ag2_hB68G5w9wVhyb7upsEw_O1qh?e=TbsDzm
https://1drv.ms/u/s!Ag2_hB68G5w9wVJBiZUQNhSWmZXT?e=aBZINk
