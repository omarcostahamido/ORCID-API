# ORCID-API

This repo includes some tips and tricks of things I learned in order to programmatically retrieve CV entries in [ORCID](https://orcid.org).

## Lessons learned

Here is what i found out:

- ORCID is open source: https://github.com/ORCID
- It has an API [[1](https://orcid.github.io/orcid-api-tutorial/)] [[2](https://info.orcid.org/hands-on-with-the-orcid-api/)] [[3](https://info.orcid.org/documentation/api-tutorials/)]
- You may not need to go through all that, if all the information you are concerned about is public on orcid, with public visibility. Here's why:
  - Note: in the following examples replace `ORCID-iD` with the orcid number that you need
  - Get `Professional Activities` (divided into `SERVICE`, `MEMBERSHIP`, and `INVITED_POSITION`), `Employment`, and `Education and Qualifications` (divided into `EDUCATION`, `DISTINCTION`, and `QUALIFICATION`):
    ```
    https://orcid.org/ORCID-iD/affiliationGroups.json
    ```
  - Get `Funding`:
    ```
    https://orcid.org/ORCID-iD/fundingGroups.json?&sort=date&sortAsc=false
    ```
  - Get `Works` (in the example below, only the first 500 entries, change the number at the end to retrieve more):
    ```
    https://orcid.org/ORCID-iD/worksExtendedPage.json?offset=0&sort=date&sortAsc=false&pageSize=500
    ```
  - Get `Bio`:
    ```
    https://orcid.org/ORCID-iD/public-record.json
    ```


## Acknowledgements

This repo was build by [OCH](https://omarcostahamido.com) at [CEIS20](https://www.uc.pt/iii/ceis20) while interacting with Olga Solovova.