# [Feature Title]


## Description
This is the general "what?" of the feature. What is your feature? Why is it important? Keep it brief and to-the-point.


## Goals
* The "why?" of this feature
* Point form
* High-level
* Not more than 5


## Post-Mortem (optional)
Initially TBD. This section is filled after development is complete.

* Mistakes
  * This should be updated as you implement the feature
  * Add anything that you missed in your original architecture
* Challenges
  * This should be updated as you implement the feature
  * Add anything that was more challenging than expected, and may have contributed to misjudgement of time
* Metrics
  * List the metrics changes that arose after the feature was shipped
  * Don't forget to compare them with your expectations
* Learnings
  * Jot down what you learned in architecting and building this feature
  * How will you improve in future feature architectures and implementations?


## Metrics (optional)
* Added
  * Every new metric that will be tracked
  * Eg. `CONVERSATION_OPENED { isRead }`
* Changed
  * Every metric that be was modified
  * Eg. `SIGNUP` segmented by `{ type: 'email'|'facebook' }`
* Removed
  * Every removed metric
  * Eg. `FACEBOOK_SIGNUP`
* Expectations
  * More
    * Events that you expect to see more of
  * Less
    * Events that you expect to see less of

Example:
* Actions
  * Added
    * `AUDIO_SEEK`
    * `AUDIO_PLAY`
    * `AUDIO_PAUSE`
    * `AUDIO_FAST_FORWARD`
    * `AUDIO_REWIND`
    * `AUDIO_TOGGLE_MUSIC`
    * `AUDIO_PLAYBACK_DONE`
* Expectations
  * More
    * SIGNUP > PREMIUM_SUBSCRIBED


## R&D
* Problem: Ask every question that you can think of regarding this feature and the challenges involved in implementing it
  * Describe results you obtained through research and development
  * What frameworks did you try? Why?
  * What information did you gather? StackOverflow answers, videos, GitHub comments, etc.
  * What assumptions did you make? How did they change? Why?
  * What had to be reverted? Why?
  * Solution: What was the final solution? Why did you pick it? List any sources.
* Problem 2: ...

Example:
* Problem: `react-native-audio-toolkit` does not support audio playback on a locked device on iOS
  * https://github.com/futurice/react-native-audio-toolkit/blob/master/docs/API.md#player-methods
  * `react-native-sound` does not support streaming
    * https://github.com/zmxv/react-native-sound/issues/353
  * Solution 1: `react-native-track-player`
    * https://github.com/react-native-kit/react-native-track-player/wiki/Background-Mode
  * Solution 2: `react-native-video`
    * https://github.com/react-native-community/react-native-video#audio-mixing
  * Conclusion: Use `react-native-track-player` since it's better suited for playing long audio files in the background.
    * Switch to `react-native-video` if something is missing there.


## Flow
* This is the "when?" and "where?" of this feature. Detailed user stories are examples of the flow.
* This happens first
* Then this
* And so forth
* Go through all scenarios


## Sub-Features
[ ] This is the specific "how?" and "what?" of this feature
[ ] Break it down
[ ] How will you achieve your goals?
[ ] Be as specific as possible
[ ] Solve all problems before they occur and discover overlappings
[ ] These checkboxes are then checked off as you implement the feature
[ ] The feature is complete once all checkboxes are checked, meaning nothing should be missing from this list
[ ] Once your architecture is merged, these can be moved to your favourite project management system

Example:
[ ] <ConversationsContainer>: A container that will act as the root for the new <Stack>, left of <NotificationsContainer>
[ ] bootyUtil
  [ ] bootyUtil.getSpanks: Get the number of spanks for the given performer
  [ ] bootyUtil.checkBooty: Checks the provided booty


## Migration (optional)
* How will the current architecture be modified to migrate to this new architecture?
* What files will be removed?
* What functions will be deprecated?
* What storage migrations will be performed


## API
* Write as much code in here as you can
* Function signatures, constants, contract interfaces, etc
* Structure sections by filenames
* Be sure to alphabetize your api sections

### [filename/path/here.js]
```js
/**
 * Fully document everything. This code is copy-pasteable for when
 * you begin the implementation phase.
 * @return {Boolean}
 */
function yoMama() {}
```

### [another/file/path.js]
Here is an example of a changed file:
```js
// ...

/**
 * This is a new function in an existing file. It is optionally wrapped in `// ...`.
 * @return {Any}
 */
function newFunction() {}

// ...

const EXISTING_CONSTANT = {

  // ...

  /**
   * This is a new property. Notice that it is surrounded by `// ...` to show
   * that it is modifying existing code.
   * @type {Object}
   */
  myNewProp: {},

  // ...

}
```

### [contract/location/wayback.sol]
Here is an example of a contract interface:
```sol
contract Wayback {
  /**
   * Keep documenting.
   */
  mapping(bytes32 => address) projectToOwner;
  mapping(bytes32 => address) eventTxHashToApproved;
  event action(bytes32 projectId, bytes32 metaData);

  function writeEvent(bytes32 projectId, bytes32 metaData) external {}
  function writeAndApprove(bytes32 projectId, bytes32 metaData, bytes32 eventTxHash, address thirdParty) external {}
  function sign(bytes32 projectId, bytes32 metaData, bytes32 eventTxHash) external {}
}
```
