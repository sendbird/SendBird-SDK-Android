## Change Log

### v3.0.101 (Sep 2, 2019)
* Improved stability.

### v3.0.100 (Aug 23, 2019)
* Improved stability.

### v3.0.99 (Aug 16, 2019)
* Improved `MetaArray` in `BaseMessage`. `MetaArray` order passed as a parameter will be kept.
   * Added `MessageMetaArray` class.
   * Added `getAllMetaArrays()` and `getMetaArrays(Collection<String> metaArrayKeys)` in `BaseMessage`.
   * Added `addMessageMetaArrayValues(BaseMessage message, List<MessageMetaArray> metaArrays, MessageMetaArrayHandler handler)` and `removeMessageMetaArrayValues(BaseMessage message, List<MessageMetaArray> metaArrays, MessageMetaArrayHandler handler)` in `BaseChannel`.
   * Deprecated `getAllMetaArray()` and `getMetaArray(Collection<String> metaArrayKeys)` in `BaseMessage`.
   * Deprecated `addMessageMetaArrayValues(BaseMessage message, Map<String, List<String>> metaArrayMap, MessageMetaArrayHandler handler)` and `removeMessageMetaArrayValues(BaseMessage message, Map<String, List<String>> metaArrayMap, MessageMetaArrayHandler handler)` in `BaseChannel`. 
* Added `resendFileMessage(FileMessage fileMessage, File file, ResendFileMessageHandler handler)` and `resendFileMessage(FileMessage fileMessage, File file, ResendFileMessageWithProgressHandler handler)` in `BaseChannel`.
* Added `getRequestState()` and `enum RequestState { NONE, PENDING, FAILED, SUCCEEDED }` in `FileMessage`.
* Added `setStrict(boolean strict)` in `GroupChannelParams`. If it is set to true, the channel creation will be failed if any of the users do not exist.
* Added `translateUserMessage(UserMessage userMessage, List<String> targetLanguages, TranslateUserMessageHandler handler)` in `BaseChannel`.
* Added `getRequestedMentionUserIds()` in `UserMessage` and `FileMessage`.

### v3.0.98 (Jul 23, 2019)
* Added `setThreadOption(ThreadOption threadOption, Handler handler)` in SendBird.Option.
* Deprecated `useUiThreadForCallbacks(boolean)` and `setHandlerForCallbacks(Handler handler)` in SendBird.Option.
* Improved stability.

### v3.0.97 (Jun 21, 2019)
* Added `setHandlerForCallbacks(Handler handler)` in SendBird.Options.
* Improved stability.

### v3.0.96 (Jun 7, 2019)
* Added `getRequestState()` and `enum RequestState { NONE, PENDING, FAILED, SUCCEEDED }` in UserMessage.
* Added `resendUserMessage(UserMessage userMessage, ResendUserMessageHandler handler)` in BaseChannel.
* Added `getMyLastRead()` in GroupChannel.
* Added `createChannelWithOperatorUserIds(String name, String channelUrl, Object coverUrlOrImage, String data, String customType, List<String> operatorUserIds, OpenChannelCreateHandler handler)` in OpenChannel.

### v3.0.95 (May 17, 2019)
* Added `delete(GroupChannelDeleteHandler handler)` in `GroupChannel`.

### v3.0.94 (May 3, 2019)
* Added `isDiscoverable` property to `GroupChannel` and `GroupChannelParams`.
  * if `isDiscoverable` of a public group channel is set to false, then the channel will not appear on the result of `PublicGroupChannelListQuery`.
  
### v3.0.93 (Apr 26, 2019)
* Improved stability.

### v3.0.92 (Apr 5, 2019)
* Improved stability.

### v3.0.91 (Mar 14, 2019)
* Improved stability.

### v3.0.90 (Feb 21, 2019)
* Fixed minor bug.

### v3.0.89 (Feb 13, 2019)
* Fixed minor bug.

### v3.0.88 (Jan 31, 2019)
* Added getter methods of `GroupChannelListQuery` and `PublicGroupChannelListQuery` properties.
* Added overriding method `equals()` in `BaseMessage`, `AdminMessage`, `FileMessage`, `UserMessage`, `User`, `Sender` and `Member`.
* Fixed minor bug.

### v3.0.87 (Jan 29, 2019)
* Fixed minor bug.

### v3.0.86 (Jan 18, 2019)
* Added `enum PushTriggerOption {ALL, OFF, MENTION_ONLY, DEFAULT}` in `GroupChannel`.
  * `ALL` : It receives all push notifications.
  * `OFF` : It doesn't receive any push notifications.
  * `MENTION_ONLY` : It receives push notifications which mention me.
  * `DEFAULT` : It receives push notifications according to the state of `PushTriggerOption` in `SendBird`.
  * `PushTriggerOption` of `GroupChannel` has higher priority than `SendBird`'s. It depends on `SendBird`'s `PushTriggerOption` only when `GroupChannel`'s `PushTriggerOption` is `DEFAULT`.
* Added `setMyPushTriggerOption(PushTriggerOption pushTriggerOption, GroupChannelSetMyPushTriggerOptionHandler handler)` in `GroupChannel`.
* Added `getMyPushTriggerOption(GroupChannelGetMyPushTriggerOptionHandler handler)` in `GroupChannel`.
* Added `enum PushTriggerOption {ALL, OFF, MENTION_ONLY}` in `SendBird`.
  * `ALL` : It receives all push notifications.
  * `OFF` : It doesn't receive any push notifications.
  * `MENTION_ONLY` : It receives push notifications which mention me.
* Added `setPushTriggerOption(PushTriggerOption pushTriggerOption, SetPushTriggerOptionHandler handler)` in `SendBird`.
* Added `getPushTriggerOption(GetPushTriggerOptionHandler handler)` in `SendBird`.
* Added `setSnoozePeriod(boolean snoozeOn, long startTs, long endTs, SetSnoozePeriodHandler handler)` in `SendBird`.
  * It snooze or stop snooze push notification in specific duration.
* Added `getSnoozePeriod(GetSnoozePeriodHandler handler)` in `SendBird`.

### v3.0.85 (Dec 14, 2018)
* Fixed minor bugs.

### v3.0.84 (Nov 30, 2018)
* Fixed minor bugs.

### v3.0.83 (Nov 22, 2018)
* Added `createDistinctChannelIfNotExist(GroupChannelParams params, GroupChannelCreateDistinctChannelIfNotExistHandler handler)` in `GroupChannel`.
   * It creates distinct channel and gets the channel with `isCreated` flag which represents whether the channel is actually created or not.
* Added `hide(boolean hidePreviousMessages, boolean allowAutoUnhide, GroupChannelHideHandler handler)` in `GroupChannel`.
* Added `unhide(GroupChannelUnhideHandler handler)` in `GroupChannel`.
* Added `getHiddenState()` in `GroupChannel`.
* Added `enum HiddenState { UNHIDDEN, HIDDEN_ALLOW_AUTO_UNHIDE, HIDDEN_PREVENT_AUTO_UNHIDE }` in `GroupChannel`.
   * `UNHIDDEN`: It's not hidden channel.
   * `HIDDEN_ALLOW_AUTO_UNHIDE`: It's hidden channel which is automatically unhidden when new message comes in.
   * `HIDDEN_PREVENT_AUTO_UNHIDE`: It's hidden channel which is not unhidden when new message comes in.
* Added `setHiddenChannelFilter(HiddenChannelFilter hiddenChannelFilter)` in `GroupChannelListQuery`.
* Added `enum HiddenChannelFilter { UNHIDDEN, HIDDEN, HIDDEN_ALLOW_AUTO_UNHIDE, HIDDEN_PREVENT_AUTO_UNHIDE }` in `GroupChannelListQuery`.
   * `UNHIDDEN`: Get all unhidden channels. (default)
   * `HIDDEN`: Get all hidden channels which `HiddenState` is `HIDDEN_ALLOW_AUTO_UNHIDE` or `HIDDEN_PREVENT_AUTO_UNHIDE`.
   * `HIDDEN_ALLOW_AUTO_UNHIDE`: Get channels which `HiddenState` is `HIDDEN_ALLOW_AUTO_UNHIDE`.
   * `HIDDEN_PREVENT_AUTO_UNHIDE`: Get channels which `HiddenState` is `HIDDEN_PREVENT_AUTO_UNHIDE`.
* Added `getMessageChangeLogsByTimestamp(long ts, GetMessageChangeLogsHandler handler)` in `BaseChannel`.
   * It retrieves message change logs since the given timestamp.

### v3.0.82 (Nov 15, 2018)
* Changed type of `getSender()` in `UserMessage` and `FileMessage` from `User` to a new class `Sender` which extends `User`.
* `Sender` has `isBlockedByMe()` which indicates that the message sender is blocked by the current user (default: false).
* `isBlockedByMe()` is valid in `GroupChannel` only.
* Message from blocked users is delivered only when block_mode in SendBird application is set to explicit mode. Otherwise, it's not visible nor delivered.
* Fixed minor bugs.

### v3.0.81 (Nov 8, 2018)
* Added `ApplicationUserListQuery`, `BlockedUserListQuery`, `ParticipantListQuery`, `MutedUserListQuery` and `BannedUserListQuery` classes.
* Added `setUserIdsFilter(List<String> userIds)` and `setMetaDataFilter(String metaDataKey, List<String> metaDataValues)` in `ApplicationUserListQuery`.
* Added `setUserIdsFilter(List<String> userIds)` in `BlockedUserListQuery`.
* Updated `createBlockedUserListQuery()` in `SendBird` to return `BlockedUserListQuery` instance.
* Updated `createBannedUserListQuery()` in `GroupChannel` to return `BannedUserListQuery` instance.
* Updated `createParticipantListQuery()` in `OpenChannel` to return `ParticipantListQuery` instance.
* Updated `createMutedUserListQuery()` in `OpenChannel` to return `MutedUserListQuery` instance.
* Updated `createBannedUserListQuery()` in `OpenChannel` to return `BannedUserListQuery` instance.
* Deprecated `UserListQuery` `createUserListQuery()` in `SendBird`.
* Deprecated `UserListQuery` `createUserListQuery(List<String> userIds)` in `SendBird`.
* Deprecated `setMetaDataFilter(String metaDataKey, List<String> metaDataValues)` in `UserListQuery`.
* Fixed minor bugs.

### v3.0.80 (Oct 31, 2018)
* Added `registerScheduledUserMessage(ScheduledUserMessageParams params, RegisterScheduledUserMessageHandler handler)` in `GroupChannel`.
* Added `ScheduledUserMessageParams` and `ScheduledUserMessage`.
* Added `setTranslationTargetLanguages(List<String> targetLanguages)` and deprecated `setTargetLanguages(List<String> targetLanguages)` in `UserMessageParams`.
* Improved stability.
* Fixed minor bugs.

### v3.0.79 (Oct 26, 2018)
* Added `getMyMutedInfo()` in `BaseChannel`.
* Added `muteUser(User user, String description, int seconds, GroupChannelMuteHandler handler)` in `GroupChannel`.
* Added `muteUserWithUserId(String userId, String description, int seconds, GroupChannelMuteHandler handler)` in `GroupChannel`.
* Added `muteUser(User user, String description, int seconds, OpenChannelMuteHandler handler)` in `OpenChannel`.
* Added `muteUserWithUserId(String userId, String description, int seconds, OpenChannelMuteHandler handler)` in `OpenChannel`.
* Added `setOrder(Order.METADATA_VALUE_ALPHABETICAL)` with `setMetaDataOrderKeyFilter()` in `GroupChannelListQuery` and `PublicGroupChannelListQuery`.

### v3.0.78 (Oct 24, 2018)
* Stabilized `updateCurrentUserInfoWithProfileImage()`.

### v3.0.77 (Oct 21, 2018)
* Added `getLastConnectedAt()` in `SendBird`.
* Fixed minor bugs.

### v3.0.76 (Oct 11, 2018)
* Improved stability.

### v3.0.75 (Sep 21, 2018)
* Added `getTotalUnreadMessageCount(GroupChannel.GroupChannelTotalUnreadMessageCountHandler handler)` in `SendBird`.
* Added `getTotalUnreadMessageCount(List<String> channelCustomTypes, GroupChannel.GroupChannelTotalUnreadMessageCountHandler handler)` in `SendBird`.
* Added `getTotalUnreadMessageCount(GroupChannelTotalUnreadMessageCountParams params, GroupChannel.GroupChannelTotalUnreadMessageCountHandler handler)` in `SendBird`.
* Added `getUnreadItemCount(Collection<GroupChannel.UnreadItemKey> keys, GroupChannel.GroupChannelGetUnreadItemCountHandler handler)` in `SendBird`.
* Added `getTotalUnreadChannelCount(GroupChannel.GroupChannelTotalUnreadChannelCountHandler handler)` in `SendBird`.
* Added `getGroupChannelCount(GroupChannelListQuery.MemberStateFilter memberStateFilter, GroupChannel.GroupChannelChannelCountHandler handler)` in `SendBird`.
* Added `getReadMembers(BaseMessage message, boolean includeAllMembers), getUnreadMembers(BaseMessage message, boolean includeAllMembers)` and `getReadStatus(boolean includeAllMembers)` in `GroupChannel`.
* Added a `ERR_CONNECTION_CANCELED` error code for the connect cancel event which usually occurs on disconnect while connecting.
* Deprecated `CLOSING` in enum `ConnectionState` in `SendBird`.
* Deprecated `createChannel(List<User> users, boolean isDistinct, String name, Object coverUrlOrImage, String data, GroupChannelCreateHandler handler)` in `GroupChannel`.
* Deprecated `createChannelWithUserIds(List<String> userIds, boolean isDistinct, String name, Object coverUrlOrImage, String data, GroupChannelCreateHandler handler)` in `GroupChannel`.
* Deprecated `updateChannel(boolean isDistinct, String name, Object coverUrlOrImage, String data, GroupChannelUpdateHandler handler)` in `GroupChannel`.
* Deprecated `getTotalUnreadMessageCount(GroupChannelTotalUnreadMessageCountHandler handler)` in `GroupChannel`.
* Deprecated `getTotalUnreadMessageCount(List<String> channelCustomTypes, GroupChannelTotalUnreadMessageCountHandler handler)` in `GroupChannel`.
* Deprecated `getTotalUnreadMessageCount(GroupChannelTotalUnreadMessageCountParams params, GroupChannelTotalUnreadMessageCountHandler handler)` in `GroupChannel`.
* Deprecated `getUnreadItemCount(Collection<UnreadItemKey> keys, GroupChannelGetUnreadItemCountHandler handler)` in `GroupChannel`.
* Deprecated `getTotalUnreadChannelCount(GroupChannelTotalUnreadChannelCountHandler handler)` in `GroupChannel`.
* Deprecated `getChannelCount(GroupChannelListQuery.MemberStateFilter memberStateFilter, GroupChannelChannelCountHandler handler)` in `GroupChannel`.
* Deprecated `getReadMembers(BaseMessage message), getUnreadMembers(BaseMessage message)` and `getReadStatus()` in `GroupChannel`.
* Deprecated `createChannel(String name, Object coverUrlOrImage, String data, OpenChannelCreateHandler handler)` in `OpenChannel`.
* Deprecated `createChannel(String name, Object coverUrlOrImage, String data, List<User> operatorUsers, OpenChannelCreateHandler handler)` in `OpenChannel`.
* Deprecated `updateChannel(String name, Object coverUrlOrImage, String data, List<User> operatorUsers, OpenChannelUpdateHandler handler)` in `OpenChannel`.
* Deprecated `sendFileMessage(File file, String name, String type, int size, String data, String customType, SendFileMessageHandler handler)` in `BaseChannel`.
* Deprecated `sendFileMessage(File file, String name, String type, int size, String data, String customType, SendFileMessageWithProgressHandler handler)` in `BaseChannel`.
* Deprecated `sendUserMessage(String message, String data, SendUserMessageHandler handler)` in `BaseChannel`.
* Deprecated `sendUserMessage(String message, String data, String customType, SendUserMessageHandler handler)` in `BaseChannel`.
* Fixed minor bugs.

### v3.0.74 (Sep 14, 2018)
* Improved stability.

### v3.0.73 (Sep 10, 2018)
* From now, `useMemberAsMessageSender()` option is true by default.
* Fixed a bug previous messages not showing the sender's latest user metadata.

### v3.0.72 (Sep 4, 2018)
* Added `SendBird.Options.useUiThreadForCallbacks()` to give developers an option for threads the callbacks are running. By default, it is UI thread but you can choose to run on background threads.
* Fixed minor bugs.

### v3.0.71 (Aug 24, 2018)
* Added `updateUserMessage()` with `UserMessageParams` in `BaseChannel`.
* Added `updateFileMessage()` with `FileMessageParams` in `BaseChannel`.
* Added `UserMessageParams()` default constructor in `UserMessageParams`.
* Added `setMessage()` in `UserMessageParams`.
* Added `FileMessageParams()` default constructor in `FileMessageParams`.
* Added `setFileUrl()` and `setFile()` in `FileMessageParams`.
* Minor bug fixed.

### v3.0.70 (Aug 20, 2018)
* Improved connection management.

### v3.0.69 (Aug 16, 2018)
* Fixed a bug occasionally occurring when a group channel is created with multiple users.
* Fixed TLS handshake related bug in Android 8.1.0.

### v3.0.68 (Aug 3, 2018)
* Added `getInvitedAt()` in `GroupChannel`.

### v3.0.67 (Jul 20, 2018)
* Minor bug fixed.

### v3.0.66 (Jul 13, 2018)
* Added `load(MessageListQueryResult handler)`, `setLimit()`, `setReverse()`, `setMessageTypeFilter()`, `setCustomTypeFilter()`, `setSenderUserIdsFilter()` in `PreviousMessageListQuery`.
* Added `getNextMessagesByTimestamp()`, `getPreviousMessagesByTimestamp()`, `getPreviousAndNextMessagesByTimestamp()`, `getNextMessagesById()`, `getPreviousMessagesById()`, `getPreviousAndNextMessagesById()` with `sendUserIds` parameter in `BaseChannel`.

### v3.0.65 (Jul 6, 2018)
* Disabled to put the current user into `mentionedUsers`, `mentionedUserIds` in `UserMessageParams` and `FileMessageParams`.
* Changed not to increase `unreadMentionCount` and not to call `onMentionReceived` for CHANNEL mention by the current user (i.e. the message sender is the current user).

### v3.0.64 (Jun 29, 2018)
* Added `getUnreadMentionCount()` in `GroupChannel`.
* Added `UNREAD_MENTION_COUNT_ONLY` in `CountPreference` in `GroupChannel`.
* Added `GROUP_CHANNEL_UNREAD_MESSAGE_COUNT`, `GROUP_CHANNEL_UNREAD_MENTION_COUNT`, `GROUP_CHANNEL_INVITATION_COUNT`, `NONSUPER_UNREAD_MENTION_COUNT`, `SUPER_UNREAD_MENTION_COUNT` in enum `UnreadItemKey` in `GroupChannel`.
* Added `getMentionType()` in `BaseMessage` with enum `MentionType { USERS, CHANNEL }` in `BaseMessageParams`.
* Added `setMentionType()` in `UserMessageParams` and `FileMessageParams`.

### v3.0.63 (Jun 22, 2018)
* Added `getMyCountPreference()` and `setMyCountPreference()` in `GroupChannel`.
* Added `setNicknameStartsWithFilter()` in `GroupChannelMemberListQuery`.

### v3.0.62 (Jun 13, 2018)
* Added `getJoinedMemberCount()` in `GroupChannel` to show the total count of joined users in a `GroupChannel`.
* Added `getMyMutedState()` in `GroupChannel` to show the state of the connected user in a `GroupChannel`.
* Added `setMemberStateFilter()` in `GroupChannelMemberListQuery` to search members based on the state of the member in a `GroupChannel`.
* Added `getUnreadItemCount()` in `GroupChannel` with `enum UnreadItemKey` { `NONSUPER_UNREAD_MESSAGE_COUNT`, `SUPER_UNREAD_MESSAGE_COUNT`, `NONSUPER_INVITATION_COUNT`, `SUPER_INVITATION_COUNT`}.

### v3.0.61 (Jun 1, 2018)
* Added a typing indicator throttle option in `SendBird.Options`.
* Fixed a minor bug when uploading file in background.

### v3.0.60 (May 16, 2018)
* Fixed an occasional member count mismatch in a super group channel.

### v3.0.59 (May 15, 2018)
* Added `getTotalUnreadMessageCount()` with `GroupChannelTotalUnreadMessageCountParams` in `GroupChannel` to support filter for total unread message count.
* Added `getMyRole()` in `GroupChannel` to specify the current user is operator of the channel or not.

### v3.0.58 (May 2, 2018)
* Now `GroupChannelMemberListQuery` returns the member list in nickname alphabetical order.
* Improved connection stability.

### v3.0.57 (Apr 19, 2018)
* Added `createOperatorListQuery()` in `BaseChannel` and `OperatorListQuery`.
* Deprecated `setOperatorFilter(OperatorFilter operatorFilter)` and `OperatorFilter` in `GroupChannelMemberListQuery`.

### v3.0.56 (Mar 29, 2018)
* Added `getTotalUnreadMessageCount()` with channel custom types filter in `GroupChannel`.
* Added `setPushNotificationDeliveryOption(PushNotificationDeliveryOption pushNotificationDeliveryOption)` in `UserMessageParams` and `FileMessageParams`.

### v3.0.55 (Mar 21, 2018)
* From now, an ephemeral `GroupChannel` maintains the last message and unread message count after the connection is made.

### v3.0.54 (Mar 15, 2018)
* Fixed `groupChannel.getMyMemberState()` returning not accurate value for the 1st time.

### v3.0.53 (Mar 12, 2018)
* Added `setConnectionTimeout()` to `SendBird.Options` to support configurable connection timeout.

### v3.0.52 (Mar 7, 2018)
* Added `setEphemeral(boolean isEphemeral)` in `GroupChannelParams` to create a channel not allowing message retention.
* Added `isEphemeral()` in `BaseChannel`.
* Added `BaseMessageParams`, `UserMessageParams` and `FileMessageParams` to send messages in object form.
   * `BaseMessageParams` support mentioned messages by `setMentionedUserIds` and `setMentionedUsers`.
* Added `sendUserMessage(UserMessageParams params, SendUserMessageHandler handler)` in `BaseChannel`.
* Added `sendFileMessage(FileMessageParams params, SendFileMessageHandler handler)` in `BaseChannel`.
* Added `sendFileMessage(FileMessageParams params, SendFileMessageWithProgressHandler handler)` in `BaseChannel`.
* Added `onMentionReceived(BaseChannel channel, BaseMessage message)` in `ChannelHandler` to receive mentioned message.
* Added `getMentionedUsers()` in `BaseMessage`.
* Added `getMyMemberState()` in `GroupChannel` for current logged-in user's joined state for the channel.
* Deprecated `MemberState` enumerator in `GroupChannel` and added `MemberStateFilter` in `GroupChannelListQuery` enumerator instead.
* Deprecated `getChannelCount(MemberState memberState, GroupChannelChannelCountHandler handler)` in `GroupChannel`.
* Added `getChannelCount(GroupChannelListQuery.MemberStateFilter memberStateFilter, GroupChannelChannelCountHandler handler)` in `GroupChannel`.
* Deprecated `setMemberStateFilter(GroupChannel.MemberState memberState)` in `GroupChannelListQuery`.
* Added `setMemberStateFilter(MemberStateFilter memberStateFilter)` in `GroupChannelListQuery`.
* Deprecated `getState()` in Member and added `getMemberState()` instead.
* Improved stabilization.
* Fix minor bug.

### v3.0.51 (Feb 22, 2018)
* Added `setOperators()` and `setOperatorUserIds()` in `GroupChannelParams`.
* Added `freeze()`, `unfreeze()` and `isFrozen()` in `GroupChannel`.
* Added `banUser()` and `banUserWithUserId()` in `GroupChannel`.
* Added `unbanUser()` and `unbanUserWithUserId()` in `GroupChannel`.
* Added `muteUser()` and `muteUserWithUserId()` in `GroupChannel`.
* Added `unmuteUser()` and `unmuteUserWithUserId()` in `GroupChannel`.
* Added `createBannedUserListQuery()` in `GroupChannel`.
* Added `setOperatorFilter()` and `setMutedMemberFilter()` in `GroupChannelMemberListQuery`.
* Modified `onUserBanned(OpenChannel channel, User user)` to `onUserBanned(BaseChannel channel, User user)` in `ChannelHandler`.
* Modified `onUserUnbanned(OpenChannel channel, User user)` to `onUserUnbanned(BaseChannel channel, User user)` in `ChannelHandler`.
* Modified `onUserMuted(OpenChannel channel, User user)` to `onUserMuted(BaseChannel channel, User user)` in `ChannelHandler`.
* Modified `onUserUnmuted(OpenChannel channel, User user)` to `onUserUnmuted(BaseChannel channel, User user)` in `ChannelHandler`.
* Modified `onChannelFrozen(OpenChannel channel, User user)` to `onChannelFrozen(BaseChannel channel, User user)` in `ChannelHandler`.
* Modified `onChannelUnfrozen(OpenChannel channel, User user)` to `onChannelUnfrozen(BaseChannel channel, User user)` in `ChannelHandler`.
* Now `sender` in `UserMessage` and `FileMessage` support `getMetaData()`.

### v3.0.50 (Feb 5, 2018)
* Added `createPublicGroupChannelListQuery()` in `GroupChannel`.
* Added `isPublic()` in `GroupChannel`.
* Added join in `GroupChannel`.
* Added `CHANNEL_NAME_ALPHABETICAL` in `Order` in `GroupChannelListQuery`.
* Added `PublicChannelFilter` in `GroupChannelListQuery`.
* Added `setCustomTypeStartsWithFilter()` in `GroupChannelListQuery`.
* Added `setPublicChannelFilter()` in `GroupChannelListQuery`.
* Added `setPublic()` in `GroupChannelParams`.
* Added `setChannelUrl()` in `GroupChannelParams`.
* Added `PublicGroupChannelListQuery`.
* Improved stabilization.

### v3.0.49 (Jan 28, 2018)
* Added `createChannel()` with `GroupChannelParams` in `GroupChannel`.
* Added `createMemberListQuery()` in `GroupChannel`.
* Added `isSuper()` in `GroupChannel`.
* Added `updateChannel()` with `GroupChannelParams` in `GroupChannel`.
* Deprecated `getLastSeenAtBy()` in `GroupChannel`.
* Deprecated `getLastSeenAtByWithUserId()` in `GroupChannel`.
* Added `SuperChannelFilter` in `GroupChannelListQuery`.
* Added `setSuperChannelFilter()` in `GroupChannelListQuery`.
* Added `GroupChannelMemberListQuery`.
* Added `GroupChannelParams`.

### v3.0.48 (Jan 16, 2018)
* Improved stabilization of calling `disconnect()` while sending messages or mark as read.
* Deprecated `markAsReadAll()` in `GroupChannel`.
* Added `INVITED_BY_FRIEND`, `INVITED_BY_NON_FRIEND` in `setMemberStateFilter()` in `GroupChannelListQuery`.
* Added `markAsReadAll()` in `SendBird`.
* Added `markAsReadWithChannelUrls()` in `SendBird`.
* Fixed Minor bugs.

### v3.0.47 (Jan 5, 2018)
* Added `FriendListQuery`.
* Added `setCustomTypesFilter()` in `GroupChannelListQuery`.
* Added `addUserEventHandler()` in `SendBird`.
* Added ``removeUserEventHandler()` in `SendBird`.
* Added `removeAllUserEventHandlers()` in `SendBird`.
* Added `addFriends()` in `SendBird`.
* Added `deleteFriends()` in `SendBird`.
* Added `deleteFriend()` in `SendBird`.
* Added `uploadFriendDiscoveries()` in `SendBird`.
* Added `deleteFriendDiscoveries()` in `SendBird`.
* Added `deleteFriendDiscovery()` in `SendBird`.
* Added `getFriendChangeLogsByToken()` in `SendBird`.
* Added `createFriendListQuery()` in `SendBird`.
* Added `getOriginalProfileUrl()` in `User`.
* Improved `ConnectHandler` callback.
* Fixed Minor bugs.

### v3.0.46 (Dec 19, 2017)
* Improved connection stability.

### v3.0.45 (Dec 8, 2017)
* Improved connection stability.
* Modified `getConnectionState()` method.
* Added `isActive()` to `User`.

### v3.0.44 (Nov 29, 2017)
* Modified `init()` method.

### v3.0.43 (Nov 25, 2017)
* Stabilized to support Android O. 

### v3.0.42 (Nov 13, 2017)
* Fixed `GroupChannel` `isHidden()` bug.

### v3.0.41 (Nov 10, 2017)
* Added `onChannelHidden()` to `ChannelHandler`.

### v3.0.40 (Nov 9, 2017)
* Fixed bugs handler for connect is not called when the application becomes foreground.

### v3.0.39 (Nov 8, 2017)
* Added `isHidden()` to `GroupChannel`.
* Stabilized connection.

### v3.0.38 (Sep 1, 2017)
* Fixed a minor bug on blocking or unblocking users. 

### v3.0.37 (Aug 29, 2017)
* Added `getChannelCount` to `GroupChannel`.
* Added `resetMyHistory` to `GroupChannel` not to load messages created before the reset.
* Added network detection and auto reconnect when the network is detected. (`SendBird.setNetworkAwarenessReconnection` is provided to enable this option - default true)

### v3.0.36 (Aug 21, 2017)
* Added `isBlockedByMe` and `isBlockingMe` flag to group channel members.
* Added `getMessageChangeLogsByToken` to channel to track updated or deleted messages.

### v3.0.35 (Aug 18, 2017)
* Added new group channel hide to give you change to select whether channel member can load previous messages when the channel reappears.
* Added user `MetaData` feature.
* Added freeze status flag to open channel.

### v3.0.34 (Aug 12, 2017)
* Added `ChannelHandler` callback on `MetaData` and `MetaCounters` creation, update and deletion.
* Added channel name filter for `GroupChannelListQuery`.
* Added `getInviter()` to `GroupChannel`.

### v3.0.33 (Jul 24, 2017)
* Minor bug fixes. 

### v3.0.32 (Jul 20, 2017)
* No more crash when profile image with special characters in the file name is uploaded. 

### v3.0.31 (Jul 15, 2017)
* Added messaging copy from one channel to other channels (Sender must be a member or participant of the channels).

### v3.0.30 (Jul 10, 2017)
* Support users to accept or decline other user's invitation to a group channel.
* Added group channel join preference for accepting invitation automatically.
* **Notice**: From this version, the return type of `GroupChannel` methods previously returning `List<User>`
such as `GroupChannel.getMembers`, `GroupChannel.getTypingMembers` and etc. now return `List<Member>`.

### v3.0.29 (Jul 4, 2017)
* Added feature to set and get push notification sound for the logged-in user.

### v3.0.28 (Jun 20, 2017)
* Fixed bug `BaseMessage.buildFromSerializedData` incurring crash for messages serialized by versions prior to v3.0.27.

### v3.0.27 (Jun 15, 2017)
* Added custom type filter to `OpenChannelListQuery` and `GroupChannelListQuery`.
* Added messaging editing feature.
* Added file uploading cancel.

### v3.0.26 (May 19, 2017)
* Added `OpenChannel` deletion.

### v3.0.25 (May 9, 2017)
* Fixed custom host bug.

### v3.0.24 (Apr 19, 2017)
* Added `connect()` custom host feature.

### v3.0.23 (Apr 12, 2017)
* Added real size property for generated thumbnails.
* Added progress handler for file uploading.
* Support file uploading on background.

### v3.0.22 (Mar 9, 2017)
* Fixed bug `GroupChannel.getUnreadMessageCount()` returning wrong value not covered on v3.0.20.

### v3.0.21 (Mar 8, 2017)
* Added `getTotalUnreadChannelCount()` to `GroupChannel` to enable you get channel count of having unread messages.
* Fixed `getTotalUnreadMessageCount()` to return correct value when it is called in `ChannelHandler.onChannelChanged` after `markAsRead()` is called.

### v3.0.20 (Mar 6, 2017)
* Added getting messages methods to `BaseChannel` and they support type/customType filtering.
* Added option for using channel member's profile URL and nickname as message sender's.
* Support updating channel member's profile URL and nickname automatically.
* Fixed bug `GroupChannel.getUnreadMessageCount()` not returning correct value.

### v3.0.19 (Mar 2, 2017)
* Added file encryption and access control feature.
* Provide serialization/deserialization for user, channel and message objects for developers to take advantage of their own local cache.
* Sender is excluded from read receipt.

### v3.0.18 (Feb 22, 2017)
* Fixed bug `GroupChannel.getReadReceipt()` always returning the count of members of the channel after the first connection.
* From now, empty string as user ID is not accepted.

### v3.0.17 (Feb 10, 2017)
* Fixed bug calling `ChannelHandler.onReadReceiptUpdated()` even when `markAsRead()` is called from the same user connected on other devices.
* Improved stability by removing occasional NPE crash on connection or reconnection.

### v3.0.16 (Jan 31, 2017)
* Added `reconnect()` to support explicit reconnection process.
* Added `removeAllConnectionHandlers()` and `removeAllChannelHandlers()`.
* Improved network call performance after reconnection is established.
* Fixed bug removing connection handlers and channel handlers when `disconnect()` is called.
* Improved stability.

### v3.0.15 (Jan 18, 2017)
* Fixed bugs returning wrong unread count of messages when users are invited to `GroupChannel`.
* Fixed bugs occurring occasional crash when `getReadReceipt()`, `getReadMembers()` or etc are called.

### v3.0.14 (Jan 4, 2017)
* Added thumbnail generating option when image file is uploaded.

### v3.0.13 (Jan 3, 2017)
* Changed connection protocol to avoid connection reset which can occur when application runs behind proxy.

### v3.0.12 (Dec 23, 2016)
* Added push notification template option, which gives option to users the way to display push notification messages.
* Improved to try connection without delay when reconnection is needed.

### v3.0.11 (Dec 16, 2016)
* Added unique push token registration option, which makes sure to maintain only one GCM/FCM token for the current user.

### v3.0.10 (Dec 7, 2016)
* Added `GroupChannel.isPushEnabled()` to check push preference for each group channel.
* Deprecated `GroupChannel.getPushPreference()`.
* Fixed randomly occurring NPE crash when user join event or read receipt update event happen.
* Improved stability.

### v3.0.9 (Nov 30, 2016)
* Added user IDs filters and query type to `GroupChannelListQuery`.
* Added channel custom type for `OpenChannel` and `GroupChannel`.
* Fixed to call `ChannelHandler.onChannelChanged` when unread message count or last message has been updated.

### v3.0.8 (Nov 23, 2016)
* Fixed to update last message of group channel when `UserMessage` or `FileMessage` is successfully sent.
* Improved stability.

### v3.0.7 (Nov 4, 2016)
* Fixed connection bug.

### v3.0.6 (Nov 3, 2016)
* Added group channel list search by a member nickname. (Search by multiple nicknames option in v3.0.5 is no more supported.)
* Added auto-translating feature to `UserMessage`.
* Improved connection performance.
* Improved stability.

### v3.0.5 (Oct 31, 2016)
* Added custom type to messages.
* Added group channel list search by member nicknames and user IDs.
* Added creating and updating channel cover image with binary file.
  
### v3.0.4 (Sep 30, 2016)
* Fixed file uploading timeout.

### v3.0.3 (Sep 27, 2016)
* Supports Android 7.0 (Nougat) and FCM.
* Fixed to increase unread message count only for others' message reception.
* Improved performance and stability.

### v3.0.2 (Sep 6, 2016)
* Added features like filtered user list, open channel keyword search, push preference setting, etc.
* Added auto background detection.
* Improved stability.

### v3.0.1 (Sep 1, 2016)
* Fixed minor bugs.

### v3.0.0 (Aug 12, 2016)
* First release.
