# Exsys's CurePlus

![cureplus logo](https://user-images.githubusercontent.com/12882714/108598469-7929c000-7396-11eb-94a3-5fd9911774b8.png)

## Documentation

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://bitbucket.org/anspire/ex-webapp/src/master/)

in this file you will find the following.

- Clone Repo
- App Structure
- How we use Git
- Create new package
- How to: Package Structure
- How to: Create Page Labels
- Build (cLoud)
- Regenrate Route
- Exsys Components
- Antd 3


## Clone Repo

- visit (https://bitbucket.org/anspire/ex-webapp/src/master/)
- login and click on Clone
- open vscode and open terminal 

```sh
  git clone git@bitbucket.org:anspire/ex-webapp.git
```
- After clone is done installing all packages and deps required for running the app
- please run the following command  at the very root of the project.
-- please make sure u have lern installed globally before running the following command
```sh 
yarn global  add lerna
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
 │   ├─> jsx-icons 
 │   ├─> labels-cache-manager #Common  APP Icons📦
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
	   
```
    ├── build                   # Compiled files (alternatively `dist`)
    ├── docs                    # Documentation files (alternatively `doc`)
    ├── src                     # Source files (alternatively `lib` or `app`)
    ├── test                    # Automated tests (alternatively `spec` or `tests`)
    ├── tools                   # Tools and utilities
    ├── LICENSE
    └── README.md
```
 
## Create New Package
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
For production environments...
 ## you will be asked to wrap your component using **labels  provider**
 > press Y
## you will be asked to wrap your component using **styled component**
 > depending if you need to create your own styled component  
 press Y/n  to create/decline
 

## How to: Package Structure
  >by default when generating package the output will be
```
|-- src
        |-- component.tsx **wrapping views from partials with labels provider*
        |-- index.interface.ts
        |-- index.ts #wrapping lazy  **component**
        |-- labelIds.json # for labels 
        |-- styled.ts
|-- package.json # will discuss next
|-- README.md  #package description
|--tsconfig.json
 
```
> addtionaly you can add the following
```
|-- page-name
    |-- src
        |-- api # not necessary  to have
            |-- api1.ts
            |-- api2.ts  
        |-- helpers  
            |-- createColumn.ts  #if your package contains table
            |-- transform.ts    #to transform object into custom model
        |-- hooks # not necessary  to have
            |-- usePopulateData.tsx
        |-- partials  # lets assuem we have form and table section
            |-- FormView.ts  
            |-- TableView.ts    
  |-- type.ts  #types
```
## How to: Create Page Labels
>exsys is 2 lanague based system (arabic & english)
to add your labels 
1- run the app ```yarn start``` then login using exysdba/123456
2- navigate to **/labels**
3- in ***table section*** search for your label if its common like ***(date from or date to)*** and select it
4- in ***poge search section*** search for your screen name like ***(rcmDhs)*** and click save
***from table section there're 2 columns, one for labelId and one for label description*** 
5- copy labelId and add it your **labelIds.json** then use it in your page
example below 

```JSX
import React, { useCallback, useEffect } from "react";
import { usePageLabelsContext } from "@app-structure/labels-provider/src";
import { PageTitle } from "@app-structure/commons/src";
const View: React.FC<TableActionViewProps> = ({
  Id,
  showModal,
  toggleModal
}) => {
   const labels = usePageLabelsContext(); //calling label provider
  return (<>
             <PageTitle
              fontsize="17px"
              children={labels.revisionandupload}
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
 

#### Regenrate Route
>lets assuem ur page route will be changed, or your page will accept param(s)
all you need to update ur package.json like below
then run``` yarn generate-routes```
this command will update routes file in  ```app->routes->pagesRoutesData.ts```
this command can be found ***in root package.json in scripts section***

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

## Antd 3
[please check ant design 3 components ](https://3x.ant.design/docs/react/introduce)
![antd](https://user-images.githubusercontent.com/12882714/108598637-65cb2480-7397-11eb-9cb2-70268dc3d71a.png) +
![react](https://user-images.githubusercontent.com/12882714/108598638-6663bb00-7397-11eb-8052-b40ecb463e47.png)
