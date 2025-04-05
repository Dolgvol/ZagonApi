### Scripts:

- **npm start** : Runs the project using `nodemon` with watching enabled.
- **npm serve** : Simply runs the application using `node`, without watch.
- **npm format** : Formats the code using `prettier` with the defined style.
- **npm lint** : Performs a code check using `eslint` to detect potential errors and style issues.
- **npm lint:fix** : Same as `lint`, but with automatic fixing of detected issues.

### Models (pseudocode):

```
type User {
    userId: ID
    createdAt: Date
    updatedAt: Date
    userName: String
    email: String
    receiveEmails: Boolean
    twoFactor: Boolean
    userRoles: [Role]
    isActive: Boolean
    passwordHash: String
    userData: UserData
}

type UserData {
    displayName?: String
    phoneNumber?: String
    firstName?: String
    lastName?: String
    avatar?: Media
    projects?: [Project]
    externalLinks?: [String]
    technology?: [Technology]
    expirience?: Expirience
}

type Role {
    roleId: ID
    roleName: String
    description?: String
    permissions: [Permission]
}

type Permission {
    permissionId: ID
    permissionName: String
    description?: String
}

type ProjectCategory {
    projectCategoryId: ID
    createdAt: Date
    updatedAt: Date
    createdBy: User
    updatedBy: User
    projectCategoryName: String
    description?: String
}

type ProjectStatus {
    projectStatusId: ID
    projectStatusName: String
}

type Project {
    projectId: ID
    createdAt: Date
    updatedAt: Date
    createdBy: User
    updatedBy: User
    projectName: String
    avatar?: Media
    status: ProjectStatus
    description?: String
    externalLinks?: [String]
    category: [ProjectCategory]
    user: [User]
    projectRoles: [Role]
    technology: [Technology]
    vacancies: [Vacancy]
}

type VacancyStatus {
    vacancyStatusId: ID
    vacancyStatusName: String
}

type Vacancy {
    vacancyId: ID
    createdAt: Date
    updatedAt: Date
    createdBy: User
    updatedBy: User
    status: VacancyStatus
    description: String
    techExpMap: Dictionary<Technology,Expirience>
}

type Technology {
    technologyId: ID
    technologyName: String
}

type Expirience {
    expirienceId: ID
    expirienceName: String
}

type Media {
    mediaId: ID,
    createdAt: Date
    updatedAt: Date
    createdBy: User
    updatedBy: User
    owner: User
    url: String,
    fileName: String,
    fileType: String
    userAvatar?: User
    projectAvatars?: [Project]
}
```
