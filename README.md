# Animal Shelter API

#### An API for animal shelters to manage their "Pets". With full CRUD functions, it includes versioning while also allowing for querying, pagination and retrieving data with GET requests.

## Authored by:
Rafael Petrachini February 2023

***

## Table of Contents
1. [Technologies Used](#technologies-used)
2. [Setup Instructions](#installation-and-setup)
3. [API Documentation](#api-documentation)
4. [Known Bugs](#known-bugs)
5. [License Information](#license)

## Technologies Used

- C#
- .NET
- Git
- Github
- Markdown
- MySQL Workbench
- Razor
- Identity
- VS Code

## Installation And Setup

### Installation Steps
1. To start, the user has to install a suitable version of .NET 6, which can be found  [here](https://dotnet.microsoft.com/en-us/download/dotnet/6.0).
2. Proceed through the installation process by following the on-screen instructions and accepting the default settings as they appear.
3. Use the terminal, such as Git Bash, to install dotnet-script by executing the indicated command.
```bash
$ dotnet tool install -g dotnet-script
```
4. Set up your local system to utilize this, instructions on how to do so can be located. [here](https://www.learnhowtoprogram.com/c-and-net/getting-started-with-c/installing-dotnet-script).
5. Then, install MySQL. Follow further detailed instructions on accomplishing that [here](https://www.learnhowtoprogram.com/c-and-net/getting-started-with-c/installing-and-configuring-mysql).

### Repository Setup
1. Clone this repository.
2. Start your shell program (e.g. Terminal or GitBash) and go to the project folder named "AnimalShelterApi.Solution".
In the folder "AnimalShelterApi.Solution/AnimalShelterApi," create a new file named "appsettings.json."
4. Open your file editor and navigate to appsettings.json
5. In the appsettings.json file, paste the following code:
```javascript
{
  "ConnectionStrings": {
      "DefaultConnection": "Server=localhost;Port=3306;database=animal_shelter_api;uid=[uid];pwd=[pwd];"
  }
}
```
6. Replace [uid] and [pwd] with your created SQL username and password respectively (including the braces).

### Create a local schema
1. Once the appsettings.json file is in place, go to the main directory of the project in the terminal.
2. Enter the command ```ef database update```
3. This will generate a database structure on your device and populate it with pre-defined data.

### Execute the Program
1. Go to the "AnimalShelterApi.Solution" production folder using the terminal.
2. Use the command line to start the program by typing `dotnet run.`

### Access the API
You can choose any API viewer of your choice, but the API is designed to work with Swagger. For more details, see the API [documentation](#api-documentation) section.



## API Documentation

### Endpoints
---
<br>

```GET/api/v2/animals```

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| name | string | Filters animals by name. |
| species | string | Filters animals by species. |
| age | int | Filters animals by age. |

#### Responses

- 200: Returns a list of animals that match the filter criteria.
- 404: Not found.
<br>
---     
<br>

```GET /api/v2/animals/{id}```

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| id | int | The id of the animal to retrieve. |

#### Responses

- 200: Returns the animal with the specified id.
- 204: No content.
- 404: Not found.
<br>
---
<br>

```POST /api/v2/animals```

#### Parameters


| Name | Type | Required? |
| ---- | ---- | ----------- |
| name | string | Yes. Max characters (20) |
| species | string | Yes |
| sex | int | Yes |


#### Responses

- 201: Returns the newly created animals object.
- 404: Not found.
<br>
---
<br>

```PUT /api/v2/animals/{id}```

#### Parameters

| Name | Type |
| ---- | ---- |
| name | string |
| species | string |
| age | int |

Note: All parameters must be entered and match existing results, only change the parameter you wish to change.

#### Responses

- 204: No content.
- 400: Bad request.
- 404: Not found.
<br>
<br>
---
<br>

```DELETE /api/v2/animals/{id}```
#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| id | int | The id of the animals to delete. |

#### Responses

- 204: No content.
- 404: Not found.
<br>
---
<br>

## Known Bugs
- None at this time.


## License
*Rafael Petrachini, January 2023. Available for distribution, modification, inspection, and application under [GPLv3 License](https://www.gnu.org/licenses/gpl-3.0.en.html)*