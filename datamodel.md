## UML Data Model for StoryBot

### Classes and Attributes

#### User
- userID: String
- userType: Enum {Child, Parent}
- name: String
- languagePreference: String

#### ChildProfile
- profileID: String
- userID: String
- age: Integer
- favoriteCharacters: List<String>
- storyPreferences: List<String>
- bedtime: Time

#### Story
- storyID: String
- title: String
- author: String
- ageGroup: Range
- language: String
- content: Text
- interactiveElements: Boolean

#### Interaction
- interactionID: String
- profileID: String
- storyID: String
- interactionTimestamp: DateTime
- duration: Integer
- choicesMade: List<String>

#### ParentControls
- controlID: String
- profileID: String
- restrictedStories: List<String>
- interactionLimits: Integer (daily interactions)
- notificationSettings: Boolean

### Relationships
- User (1) -- (1..*) ChildProfile
- ChildProfile (1) -- (0..*) Interaction
- Story (1) -- (0..*) Interaction
- ChildProfile (1) -- (1) ParentControls

