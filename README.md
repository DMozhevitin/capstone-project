## StudentSportClub

StudentSportClub is an application for students built in Daml that allows students to use free sport service provided by university on a subscription basis.

### I. Overview

Student can create `SSCApplication` contract. University can review this application and create student's personal account (represented by `SSCAccount` contract) in the student sport club. Having this account, the student receives a free access to one of the type of sport services (gym/swimming pool/tennis court) for a certain period of time. Student can only have one account in the system. The student is able to change the sport service type of their account at any time, as well as renew the account when it has expired.

### II. Workflow

1. Student creates `SSCApplication contract` (it can be done by exercising `CreateBlankApplication` choice on `UniversityService` contract for convenience)
2. Student exercises `SubmitApplication` choice on `SSCApplication`
3. University exercises `ReviewApplication` choice on `SSCApplication` and approves the account creation if student doesn't already have an account.
4. Student exercises `ChangeSportType` choice on their active `SSCAccount` to change the sport type.
5. Student exercises `RenewAccount` choice on their expired `SSCAccount` to renew the subscription to student sport club.

### III. Compiling & Testing

Manually run test scripts in `daml/Test.daml` or use

```
$ daml start
```
