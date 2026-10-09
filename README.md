
# MAST5112 ICE Task 3 – Album Collection & Debugging

## 1. Introduction

The Album Collection application is a React Native application developed using Expo and TypeScript. It allows users to enter album information, validate the information, add albums to a favourites collection, view the collection, and delete albums.

The purpose of this task was to investigate the supplied application, identify intentional errors, correct the code, and test the application's functionality.

## 2. Development Environment

The application was developed and tested using:

- Institutional virtual machine (VM)
- Visual Studio Code
- React Native
- Expo
- TypeScript
- BlueStacks 5 emulator
- Expo Go

## 3. Error Log

| # | Location | Problem | Error Type | Correction |
|---|---|---|---|---|
| 1 | `validateForm` – title | The incorrect `&&` operator prevented the title length validation from rejecting out-of-range lengths. | Logic | Changed `&&` to `||`. |
| 2 | `validateForm` – artist | The incorrect `&&` operator prevented the artist length validation from rejecting out-of-range lengths. | Logic | Changed `&&` to `||`. |
| 3 | `validateForm` – year | The validation did not reject years later than the current year. | Validation | Added a check for years greater than the current year. |
| 4 | `validateForm` – rating | Ratings greater than 5 were accepted. | Validation | Added a maximum rating check. |
| 5 | `handleSave` – album object | Numeric year and rating values did not match the string properties declared in the `Album` type. | TypeScript | Kept the values as strings to match the declared type. |
| 6 | `handleSave` – collection state | Adding an album replaced the existing collection. | State management | Used the existing array and appended the new album. |
| 7 | `handleDelete` | The filter condition retained the album selected for deletion. | Logic | Changed `===` to `!==` so the selected album is removed. |
| 8 | Genre `Picker` | The selected value was connected to the album title state. | State management | Connected `selectedValue` to `genre`. |
| 9 | Genre `Picker.Item` | Every option used the selected genre as its value instead of its own genre. | Logic | Set each option's value to `item`. |
| 10 | `FlatList` | The album title was used as the list key, although titles may not be unique. | List rendering | Used the album's unique ID as the key. |

## 4. Testing

The application was tested using the BlueStacks 5 emulator with Expo Go.

Record the actual results of the following tests:

| Test | Expected result | Actual result |
|---|---|---|
| Launch application | Application opens successfully. | [Enter result] |
| Invalid title | Title shorter than 2 characters is rejected. | [Enter result] |
| Invalid year | Years outside the permitted range are rejected. | [Enter result] |
| Invalid rating | Ratings outside 1–5 are rejected. | [Enter result] |
| Add valid album | Album is added to the collection. | [Enter result] |
| Add multiple albums | All albums remain visible. | [Enter result] |
| Delete an album | Only the selected album is removed. | [Enter result] |
| Continue after deletion | Application continues functioning. | [Enter result] |

## 5. Screenshot

Insert a screenshot showing the completed Album Collection application running in BlueStacks 5 using Expo Go.

Save the screenshot in the project folder as `screenshot.png`.

![Album Collection application running in BlueStacks 5](./screenshot.png)

## 6. Conclusion

This task provided an opportunity to investigate and debug an existing React Native application. I learned how logical conditions affect validation, how TypeScript types must match the values assigned to objects, and how React state can be used to add and remove records from an array. I also learned the importance of testing an application after correcting errors to confirm that its functionality works as expected.
