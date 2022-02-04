# Deprecated classes, methods, properties

## v3.1.6
### Classes

| Old class                  | New method                   |
| -------------------------- | --------------------------- |
| `ConnectionManager` | `SendBird.connect(String, ConnectHandler)` |

### Methods

| Old class           | Old method                     | New class           | New method                         |
| ------------------- | ------------------------------ | ------------------- | ---------------------------------- |
| `SendBird.Options` | `setAuthenticationTimeout(int)` | `SendBird.Options` | `setConnectionTimeout(int)` |


## v3.1.0

### Methods
| Old class           | Old method                     | New class           | New method                         |
| ------------------- | ------------------------------ | ------------------- | ---------------------------------- |
| `SendBird` | `init(String, Context)` | `SendBird` | `init(String, Context, boolean, InitResultHandler)` |
| `SendBird` | `initFromForeground(String, Context)` | `SendBird` | `initFromForeground(String, Context, boolean, InitResultHandler)` |
| `MessageListParams` | `setIncludeReplies()` | `MessageListParams` | `setReplyTypeFilter(ReplyTypeFilter)` |
| `MessageChangeLogsParams` | `setIncludeReplies(boolean)` | `MessageChangeLogsParams` | `setReplyTypeFilter(ReplyTypeFilter)` |
| `PreviousMessageListQuery` | `setIncludeReplies(boolean)` | `PreviousMessageListQuery` | `setReplyTypeFilter(ReplyTypeFilter)` |
| `MessageListParams` | `getIncludeReplies()` | `MessageListParams` | `getReplyTypeFilter()` |
| `MessageChangeLogsParams` | `getIncludeReplies(boolean)` | `MessageChangeLogsParams` | `getReplyTypeFilter()` |
| `PreviousMessageListQuery` | `getIncludeReplies()` | `PreviousMessageListQuery` | `getReplyTypeFilter()` |
| `MessageListParams` | `setIncludeParentMessageText()` | `MessageListParams` | `setReplyTypeFilter()` |
| `MessageChangeLogsParams` | `setIncludeParentMessageText()` | `MessageChangeLogsParams` | `setReplyTypeFilter()` |
| `PreviousMessageListQuery` | `setIncludeParentMessageText()` | `PreviousMessageListQuery` | `setReplyTypeFilter()` |
| `MessageListParams` | `shouldIncludeParentMessageText(boolean)` | `MessageListParams` | `setMessagePayloadFilter(MessagePayloadFilter)` |
| `MessageChangeLogsParams` | `shouldIncludeParentMessageText(boolean)` | `MessageChangeLogsParams` | `setMessagePayloadFilter(MessagePayloadFilter)` |
| `PreviousMessageListQuery` | `shouldIncludeParentMessageText(boolean)` | `PreviousMessageListQuery` | `setMessagePayloadFilter(MessagePayloadFilter)` |

## v3.0.172

### Methods
| Old class           | Old method                     | New class           | New method                         |
| ------------------- | ------------------------------ | ------------------- | ---------------------------------- |
| `GroupChannel` | `markAsRead()` | `GroupChannel` | `markAsRead(SendBird.MarkAsReadHandler)` |

## v3.0.170

### Methods
| Old class           | Old method                     | New class           | New method                         |
| ------------------- | ------------------------------ | ------------------- | ---------------------------------- |
| `BaseChannel` | `getNextMessagesByTimestamp(long, boolean, int, boolean, MessageTypeFilter, String, GetMessagesHandler)` | `BaseChannel` | `getMessagesByTimestamp(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getNextMessagesByTimestamp(long, boolean, int, boolean, MessageTypeFilter, String, List<String>, GetMessagesHandler)` | `BaseChannel` | `getMessagesByTimestamp(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getNextMessagesByTimestamp(long, boolean, int, boolean, MessageTypeFilter, String, List<String>, boolean, GetMessagesHandler)` | `BaseChannel` | `getMessagesByTimestamp(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getNextMessagesByTimestamp(long, boolean, int, boolean, MessageTypeFilter, String, List<String>, boolean, boolean, GetMessagesHandler)` | `BaseChannel` | `getMessagesByTimestamp(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousMessagesByTimestamp(long, boolean, int, boolean, MessageTypeFilter, String, GetMessagesHandler)` | `BaseChannel` | `getMessagesByTimestamp(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousMessagesByTimestamp(long, boolean, int, boolean, MessageTypeFilter, String, List<String>, GetMessagesHandler)` | `BaseChannel` | `getMessagesByTimestamp(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousMessagesByTimestamp(long, boolean, int, boolean, MessageTypeFilter, String, List<String>, boolean, GetMessagesHandler)` | `BaseChannel` | `getMessagesByTimestamp(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousMessagesByTimestamp(long, boolean, int, boolean, MessageTypeFilter, String, List<String>, boolean, boolean, GetMessagesHandler)` | `BaseChannel` | `getMessagesByTimestamp(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousAndNextMessagesByTimestamp(long, int, int, boolean, MessageTypeFilter, String, GetMessagesHandler)` | `BaseChannel` | `getMessagesByTimestamp(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousAndNextMessagesByTimestamp(long, int, int, boolean, MessageTypeFilter, String, List<String>, GetMessagesHandler)` | `BaseChannel` | `getMessagesByTimestamp(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousAndNextMessagesByTimestamp(long, int, int, boolean, MessageTypeFilter, String, List<String>, boolean, GetMessagesHandler)` | `BaseChannel` | `getMessagesByTimestamp(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousAndNextMessagesByTimestamp(long, int, int, boolean, MessageTypeFilter, String, List<String>, boolean, boolean, GetMessagesHandler)` | `BaseChannel` | `getMessagesByTimestamp(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getNextMessagesById(long, boolean, int, boolean, MessageTypeFilter, String, GetMessagesHandler)` | `BaseChannel` | `getMessagesByMessageId(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getNextMessagesById(long, boolean, int, boolean, MessageTypeFilter, String, List<String>, GetMessagesHandler)` | `BaseChannel` | `getMessagesByMessageId(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getNextMessagesById(long, boolean, int, boolean, MessageTypeFilter, String, List<String>, boolean, GetMessagesHandler)` | `BaseChannel` | `getMessagesByMessageId(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getNextMessagesById(long, boolean, int, boolean, MessageTypeFilter, String, List<String>, boolean, boolean, GetMessagesHandler)` | `BaseChannel` | `getMessagesByMessageId(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousMessagesById(long, boolean, int, boolean, MessageTypeFilter, String, GetMessagesHandler)` | `BaseChannel` | `getMessagesByMessageId(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousMessagesById(long, boolean, int, boolean, MessageTypeFilter, String, List<String>, GetMessagesHandler)` | `BaseChannel` | `getMessagesByMessageId(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousMessagesById(long, boolean, int, boolean, MessageTypeFilter, String, List<String>, boolean, GetMessagesHandler)` | `BaseChannel` | `getMessagesByMessageId(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousMessagesById(long, boolean, int, boolean, MessageTypeFilter, String, List<String>, boolean, boolean, GetMessagesHandler)` | `BaseChannel` | `getMessagesByMessageId(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousAndNextMessagesById(long, int, int, boolean, MessageTypeFilter, String, GetMessagesHandler)` | `BaseChannel` | `getMessagesByMessageId(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousAndNextMessagesById(long, int, int, boolean, MessageTypeFilter, String, List<String>, GetMessagesHandler)` | `BaseChannel` | `getMessagesByMessageId(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousAndNextMessagesById(long, int, int, boolean, MessageTypeFilter, String, List<String>, boolean, GetMessagesHandler)` | `BaseChannel` | `getMessagesByMessageId(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getPreviousAndNextMessagesById(long, int, int, boolean, MessageTypeFilter, String, List<String>, boolean, boolean, GetMessagesHandler)` | `BaseChannel` | `getMessagesByMessageId(long, MessageListParams, GetMessagesHandler)` |
| `BaseChannel` | `getMessageChangeLogsByToken(String, GetMessageChangeLogsByTokenHandler)` | `BaseChannel` | `getMessageChangeLogsSinceToken(String, MessageChangeLogsParams, GetMessageChangeLogsHandler)` |
| `BaseChannel` | `getMessageChangeLogsByToken(String, boolean, GetMessageChangeLogsByTokenHandler)` | `BaseChannel` | `getMessageChangeLogsSinceToken(String, MessageChangeLogsParams, GetMessageChangeLogsHandler)` |
| `BaseChannel` | `getMessageChangeLogsByToken(String, boolean, boolean, GetMessageChangeLogsByTokenHandler)` | `BaseChannel` | `getMessageChangeLogsSinceToken(String, MessageChangeLogsParams, GetMessageChangeLogsHandler)` |
| `BaseChannel` | `getMessageChangeLogsByTimestamp(long, GetMessageChangeLogsHandler)` | `BaseChannel` | `getMessageChangeLogsSinceTimestamp(long, MessageChangeLogsParams, GetMessageChangeLogsHandler)` |
| `BaseChannel` | `getMessageChangeLogsByTimestamp(long, boolean, GetMessageChangeLogsHandler)` | `BaseChannel` | `getMessageChangeLogsSinceTimestamp(long, MessageChangeLogsParams, GetMessageChangeLogsHandler)` |
| `BaseChannel` | `getMessageChangeLogsByTimestamp(long, boolean, boolean, GetMessageChangeLogsHandler)` | `BaseChannel` | `getMessageChangeLogsSinceTimestamp(long, MessageChangeLogsParams, GetMessageChangeLogsHandler)` |

## v3.0.162

### Methods
| Old class           | Old method                     | New class           | New method                         |
| ------------------- | ------------------------------ | ------------------- | ---------------------------------- |
| `ThreadMessageListParams` | `ThreadMessageListParams(int, int, BaseChannel.MessageTypeFilter, String, Collection, List, boolean, boolean, boolean, boolean, boolean)` | `ThreadMessageListParams` | `ThreadMessageListParams#ThreadMessageListParams(int, int, BaseChannel.MessageTypeFilter, Collection, List, boolean, boolean, boolean, boolean, boolean)}`, and `ThreadMessageListParams(int, int, BaseChannel.MessageTypeFilter, String, List, boolean, boolean, boolean, boolean, boolean)}` |

## v3.0.158

### Properties
| Old class           | Old property                     | New class           | New property                         |
| ------------------- | ------------------------------ | ------------------- | ---------------------------------- |
| `SendBirdError` | `ERR_ACCESS_TOKEN_NOT_VALID` | `SendBirdError` | `ERR_INVALID_TOKEN` |
| `SendBirdError` | `ERR_SESSION_TOKEN_EXPIRED`        | `SendBirdError` | `ERR_INVALID_TOKEN` |

## v3.0.152

### Methods

| Old class           | Old method                     | New class           | New method                         |
| ------------------- | ------------------------------ | ------------------- | ---------------------------------- |
| `OpenChannelParams` | `addOperatorIds(List<String>)` | `OpenChannelParams` | `setOperatorUserIds(List<String>)` |
| `OpenChannelParams` | `addOperatorId(String)`        | `OpenChannelParams` | `setOperatorUserIds(List<String>)` |
| `OpenChannelParams` | `addOperators(List<User>)`     | `OpenChannelParams` | `setOperators(List<User>)`         |
| `OpenChannelParams` | `addOperatorId(User)`          | `OpenChannelParams` | `setOperators(List<User>)`         |



## v3.0.151

### Methods

| Old class      | Old method                                                   | New class      | New method                                                   |
| -------------- | ------------------------------------------------------------ | -------------- | ------------------------------------------------------------ |
| `GroupChannel` | `setPushPreference(boolean, GroupChannelSetPushPreferenceHandler)` | `GroupChannel` | `setMyPushTriggerOption(PushTriggerOption, GroupChannelSetMyPushTriggerOptionHandler)` |
| `BaseMessage`  | `static BaseMessage build(JsonElement, String, String)`      | `BaseMessage`  | `static BaseMessage createMessage(JsonElement, String, BaseChannel.ChannelType)` |



## v3.0.150

### Methods

| Old class      | Old method                            | New class  | New method                         |
| -------------- | ------------------------------------- | ---------- | ---------------------------------- |
| `SendBird`     | `static void markAsDelivered(String)` | `SendBird` | `static void markAsDelivered(Map)` |
| `GroupChannel` | `markAsDelivered()`                   | `SendBird` | `static void markAsDelivered(Map)` |



## v3.0.145

### Methods

| Old class      | Old method           | New class      | New method         |
| -------------- | -------------------- | -------------- | ------------------ |
| `GroupChannel` | `getTypingMembers()` | `GroupChannel` | `getTypingUsers()` |



## v3.0.136

### Methods

| Old class      | Old method                                          | New class      | New method                                   |
| -------------- | --------------------------------------------------- | -------------- | -------------------------------------------- |
| `GroupChannel` | `getReadReceipt(BaseMessage)`                       | `GroupChannel` | `getUnreadMemberCount(BaseMessage)`          |
| `GroupChannel` | `getDeliveryReceipt(BaseMessage)`                   | `GroupChannel` | `getUndeliveredMemberCount(BaseMessage)`     |
| `SendBird`     | `static void notifyActivityResumedForOldAndroids()` | `SendBird`     | `static setAutoBackgroundDetection(boolean)` |
| `SendBird`     | `static void notifyActivityPausedForOldAndroids()`  | `SendBird`     | `static setAutoBackgroundDetection(boolean)` |



## v3.0.130

### Properties

| Old class     | Old property         | New class                 | New property |
| ------------- | -------------------- | ------------------------- | ------------ |
| `BaseChannel` | `CHANNEL_TYPE_OPEN`  | `BaseChannel.ChannelType` | `OPEN`       |
| `BaseChannel` | `CHANNEL_TYPE_GROUP` | `BaseChannel.ChannelType` | `GROUP`      |



## v3.0.131

### Methods

| Old class  | Old method                                                   | New class  | New method                                                   |
| ---------- | ------------------------------------------------------------ | ---------- | ------------------------------------------------------------ |
| `SendBird` | `static void getMyGroupChannelChangeLogsByToken(String, List<String>, GetMyGroupChannelChangeLogsHandler)` | `SendBird` | `static getMyGroupChannelChangeLogsByTokenWithParams(String, GroupChannelChangeLogsParams, GetMyGroupChannelChangeLogsHandler)` |
| `SendBird` | `static void getMyGroupChannelChangeLogsByToken(String, List<String>, boolean, GetMyGroupChannelChangeLogsHandler)` | `SendBird` | `static getMyGroupChannelChangeLogsByTokenWithParams(String, GroupChannelChangeLogsParams, GetMyGroupChannelChangeLogsHandler)` |
| `SendBird` | `static void getMyGroupChannelChangeLogsByTimestamp(long, List<String>, GetMyGroupChannelChangeLogsHandler)` | `SendBird` | `static getMyGroupChannelChangeLogsByTimestampWithParams(long, GroupChannelChangeLogsParams, GetMyGroupChannelChangeLogsHandler)` |
| `SendBird` | `static void getMyGroupChannelChangeLogsByTimestamp(long, List<String>, boolean, GetMyGroupChannelChangeLogsHandler)` | `SendBird` | `static getMyGroupChannelChangeLogsByTimestampWithParams(long, GroupChannelChangeLogsParams, GetMyGroupChannelChangeLogsHandler)` |



## v3.0.129

### Methods

| Old class           | Old method                       | New class           | New method                    |
| ------------------- | -------------------------------- | ------------------- | ----------------------------- |
| `FileMessageParams` | `setMetaArrayKeys(List<String>)` | `FileMessageParams` | `setMetaArrays(List<String>)` |
| `UserMessageParams` | `setMetaArrayKeys(List<String>)` | `UserMessageParams` | `setMetaArrays(List<String>)` |



## v3.0.120

### Methods

| Old class     | Old method          | New class     | New method           |
| ------------- | ------------------- | ------------- | -------------------- |
| `FileMessage` | `getRequestState()` | `BaseMessage` | `getSendingStatus()` |
| `UserMessage` | `getRequestState()` | `BaseMessage` | `getSendingStatus()` |

### Classes

| Old class                  | New class                   |
| -------------------------- | --------------------------- |
| `UserMessage#RequestState` | `BaseMessage#SendingStatus` |
| `FileMessage#RequestState` | `BaseMessage#SendingStatus` |



## v3.0.99

### Methods

| Old class              | Old method                                                   | New class              | New method                                                   |
| ---------------------- | ------------------------------------------------------------ | ---------------------- | ------------------------------------------------------------ |
| `BaseChannel`          | `addMessageMetaArrayValues(BaseMessage, Map<String, List<String>>, MessageMetaArrayHandler)` | `BaseChannel`          | `addMessageMetaArrayValues(BaseMessage, List<String>, MessageMetaArrayHandler)` |
| `BaseChannel`          | `removeMessageMetaArrayValues(BaseMessage, Map<String, List<String>>, MessageMetaArrayHandler)` | `BaseChannel`          | `removeMessageMetaArrayValues(BaseMessage, List<String>, MessageMetaArrayHandler)` |
| `BaseMessage`          | `Map<String, List<String>> getMetaArray(Collection<String>)` | `BaseMessage`          | `List<String> getMetaArrays(Collection<String>)`             |
| `ScheduledUserMessage` | `Map<String, List<String>> getAllMetaArray()`                | `ScheduledUserMessage` | `List<String> getAllMetaArrays()`                            |
| `ScheduledUserMessage` | `Map<String, List<String>> getMetaArray()                    | `ScheduledUserMessage` | `List<String> getMetaArrays(Collection<String>)`             |



## v3.0.98

### Methods

| Old class         | Old method                                     | New class     | New method                                           |
| ----------------- | ---------------------------------------------- | ------------- | ---------------------------------------------------- |
| `SendBird.Option` | `static void useUiThreadForCallbacks(boolean)` | `BaseMessage` | `static void setThreadOption(ThreadOption, Handler)` |
| `SendBird.Option` | `static void setHandlerForCallbacks(Handler)`  | `BaseMessage` | ``static setThreadOption(ThreadOption, Handler)``    |



## v3.0.86

### Methods

| Old class      | Old method                | New class      | New method                                   |
| -------------- | ------------------------- | -------------- | -------------------------------------------- |
| `GroupChannel` | `boolean isPushEnabled()` | `GroupChannel` | `PushTriggerOption getMyPushTriggerOption()` |



## v3.0.81

### Methods

| Old class       | Old method                                               | New class  | New method                                                   |
| --------------- | -------------------------------------------------------- | ---------- | ------------------------------------------------------------ |
| `SendBird`      | `static UserListQuery createUserListQuery()`             | `SendBird` | `static ApplicationUserListQuery createApplicationUserListQuery()` |
| `SendBird`      | `static UserListQuery createUserListQuery(List<String>)` | `SendBird` | `static ApplicationUserListQuery createApplicationUserListQuery()` with `ApplicationUserListQuery#setMetaDataFilter(String, List<String>)` |
| `UserListQuery` | `setMetaDataFilter(String, List<String>)`                | `SendBird` | `static ApplicationUserListQuery createApplicationUserListQuery()` with `ApplicationUserListQuery#setMetaDataFilter(String, List<String>)` |



## v3.0.80

### Methods

| Old class           | Old method                                           | New class           | New method                                                   |
| ------------------- | ---------------------------------------------------- | ------------------- | ------------------------------------------------------------ |
| `UserMessageParams` | `UserMessageParams setTargetLanguages(List<String>)` | `UserMessageParams` | `UserMessageParams setTranslationTargetLanguages(List<String>)` |



## v3.0.79

### Methods

| Old class     | Old method                                    | New class           | New method                        |
| ------------- | --------------------------------------------- | ------------------- | --------------------------------- |
| `BaseMessage` | `Map<String, List<String>> getAllMetaArray()` | `UserMessageParams` | `List<String> getAllMetaArrays()` |



## v3.0.75

### Methods

| Old class      | Old method                                                   | New class      | New method                                                   |
| -------------- | ------------------------------------------------------------ | -------------- | ------------------------------------------------------------ |
| `BaseChannel`  | `FileMessage sendFileMessage(File, String, String, int, String, String, SendFileMessageHandler)` | `BaseChannel`  | `FileMessage sendFileMessage(FileMessageParams, SendFileMessageHandler)` |
| `BaseChannel`  | `FileMessage sendFileMessage(File, String, String, int, String, String, SendFileMessageWithProgressHandler)` | `BaseChannel`  | `FileMessage sendFileMessage(FileMessageParams, SendFileMessageWithProgressHandler)` |
| `BaseChannel`  | `UserMessage sendUserMessage(String, String, SendUserMessageHandler)` | `BaseChannel`  | `UserMessage sendUserMessage(UserMessageParams, SendUserMessageHandler)` |
| `BaseChannel`  | `UserMessage sendUserMessage(String, String, String, SendUserMessageHandler)` | `BaseChannel`  | `UserMessage sendUserMessage(UserMessageParams, SendUserMessageHandler)` |
| `GroupChannel` | `static void createChannel(List<User>, boolean, String, Object, String,  GroupChannelCreateHandler) throws ClassCastException` | `GroupChannel` | `static void createChannel(GroupChannelParams, GroupChannelCreateHandler) throws ClassCastException` |
| `GroupChannel` | `static void createChannelWithUserIds(List<String>, boolean, String, Object, String, GroupChannelCreateHandler) throws ClassCastException` | `GroupChannel` | `static void createChannel(GroupChannelParams, GroupChannelCreateHandler) throws ClassCastException` |
| `GroupChannel` | `static void getTotalUnreadMessageCount(GroupChannelTotalUnreadMessageCountHandler)` | `SendBird`     | `static void getTotalUnreadMessageCount(GroupChannel.GroupChannelTotalUnreadMessageCountHandler)` |
| `GroupChannel` | `static void getTotalUnreadMessageCount(List<String>, GroupChannelTotalUnreadMessageCountHandler)` | `SendBird`     | `static void getTotalUnreadMessageCount(List<String>, GroupChannel.GroupChannelTotalUnreadMessageCountHandler)` |
| `GroupChannel` | `static void getTotalUnreadMessageCount(GroupChannelTotalUnreadMessageCountParams, GroupChannelTotalUnreadMessageCountHandler)` | `SendBird`     | `static void getTotalUnreadMessageCount(GroupChannelTotalUnreadMessageCountParams, GroupChannel.GroupChannelTotalUnreadMessageCountHandler)` |
| `GroupChannel` | `static void getUnreadItemCount(Collection<UnreadItemKey>, GroupChannelGetUnreadItemCountHandler)` | `SendBird`     | `static void getUnreadItemCount(Collection<UnreadItemKey>, GroupChannel.GroupChannelGetUnreadItemCountHandler)` |
| `GroupChannel` | `static void getTotalUnreadChannelCount(GroupChannelTotalUnreadChannelCountHandler)` | `SendBird`     | `static void getTotalUnreadChannelCount(GroupChannel.GroupChannelTotalUnreadChannelCountHandler)` |
| `GroupChannel` | `static void getChannelCount(GroupChannelListQuery.MemberStateFilter, GroupChannelChannelCountHandler)` | `SendBird`     | `static void getGroupChannelCount(GroupChannelListQuery.MemberStateFilter, GroupChannel.GroupChannelChannelCountHandler)` |
| `GroupChannel` | `updateChannel(boolean, String, Object, String, GroupChannelUpdateHandler) throws ClassCastException` | `GroupChannel` | `updateChannel(GroupChannelParams, GroupChannelUpdateHandler)` |
| `GroupChannel` | `List<Member> getReadMembers(BaseMessage)`                   | `GroupChannel` | `List<Member> getReadMembers(BaseMessage, boolean)`          |
| `GroupChannel` | `List<Member> getUnreadMembers(BaseMessage)`                 | `GroupChannel` | `List<Member> getUnreadMembers(BaseMessage, boolean)`        |
| `GroupChannel` | `Map<String, ReadStatus> getReadStatus()`                    | `GroupChannel` | `Map<String, ReadStatus> getReadStatus(boolean)`             |
| `OpenChannel`  | `static void createChannel(String, Object, String, OpenChannelCreateHandler) throws ClassCastException` | `OpenChannel`  | `static void createChannel(String, Object, String, String, List<User>, OpenChannelCreateHandler)` |
| `OpenChannel`  | `static void createChannel(String, Object, String, List<User>, OpenChannelCreateHandler) throws ClassCastException` | `OpenChannel`  | `static void createChannel(String, Object, String, String, List<User>, OpenChannelCreateHandler)` |
| `OpenChannel`  | `updateChannel(String, Object, String, List<User>, OpenChannelUpdateHandler)` | `OpenChannel`  | `static void updateChannel(String, Object, String, String, List<User>, OpenChannelUpdateHandler)` |

### Properties

| Old class  | Old property | New class | New property |
| ---------- | ------------ | --------- | ------------ |
| `SendBird` | `CLOSING`    |           |              |



## v3.0.52

### Methods

| Old class               | Old method                                                   | New class               | New method                                                   |
| ----------------------- | ------------------------------------------------------------ | ----------------------- | ------------------------------------------------------------ |
| `GroupChannel`          | `static void getChannelCount(MemberState, GroupChannelChannelCountHandler)` | `SendBird`              | `static void getChannelCount(GroupChannelListQuery.MemberStateFilter, GroupChannelChannelCountHandler)` |
| `GroupChannelListQuery` | `setMemberStateFilter(GroupChannel.MemberState)`             | `GroupChannelListQuery` | `setMemberStateFilter(MemberStateFilter)`                    |
| `Member`                | `InvitationState getState()`                                 | `Member`                | `MemberState getMemberState()`                               |

### Classes

| Old class                  | New class                                                    |
| -------------------------- | ------------------------------------------------------------ |
| `GroupChannel#MemberState` | `GroupChannelListQuery#GroupChannelListQuery.MemberStateFilter` |
| `Member#InvitationState`   | `Member#MemberState`                                         |



## v3.0.49

### Methods

| Old class      | Old method                               |
| -------------- | ---------------------------------------- |
| `GroupChannel` | `long getLastSeenAtBy(User)`             |
| `GroupChannel` | `long getLastSeenAtByWithUserId(String)` |



## v3.0.48

### Methods

| Old class      | Old method                                                 | New class  | New method                                              |
| -------------- | ---------------------------------------------------------- | ---------- | ------------------------------------------------------- |
| `GroupChannel` | `static void markAsReadAll(GroupChannelMarkAsReadHandler)` | `SendBird` | `static void markAsReadAll(SendBird.MarkAsReadHandler)` |

### Classes

| Old class                                    | New class                    |
| -------------------------------------------- | ---------------------------- |
| `GroupChannel#GroupChannelMarkAsReadHandler` | `SendBird#MarkAsReadHandler` |



## 

## v3.0.47

### Methods

| Old class               | Old method                    | New class               | New method                           |
| ----------------------- | ----------------------------- | ----------------------- | ------------------------------------ |
| `GroupChannelListQuery` | `setCustomTypeFilter(String)` | `GroupChannelListQuery` | `setCustomTypesFilter(List<String>)` |



## v3.0.37

### Methods

| Old class               | Old method                          | New class               | New method                                       |
| ----------------------- | ----------------------------------- | ----------------------- | ------------------------------------------------ |
| `GroupChannelListQuery` | `setMemberStateFilter(MemberState)` | `GroupChannelListQuery` | `setMemberStateFilter(GroupChannel.MemberState)` |

### Classes

| Old class                           | New class                  |
| ----------------------------------- | -------------------------- |
| `GroupChannelListQuery#MemberState` | `GroupChannel#MemberState` |



## v3.0.25

### Methods

| Old class     | Old method                                  | New class     | New method                                                   |
| ------------- | ------------------------------------------- | ------------- | ------------------------------------------------------------ |
| `BaseChannel` | `MessageListQuery createMessageListQuery()` | `BaseChannel` | `getNextMessagesByTimestamp(long, boolean, int, boolean, MessageTypeFilter, String, List, boolean, boolean, GetMessagesHandler)` and `getPreviousMessagesByTimestamp(long, boolean, int, boolean, MessageTypeFilter, String, List, boolean, boolean, GetMessagesHandler)` |

### Classes

| Old class          | New class                                                    |
| ------------------ | ------------------------------------------------------------ |
| `MessageListQuery` | `BaseChannel#getNextMessagesByTimestamp(long, boolean, int, boolean, BaseChannel.MessageTypeFilter, String, List, boolean, boolean, BaseChannel.GetMessagesHandler)` and `BaseChannel#getPreviousMessagesByTimestamp(long, boolean, int, boolean, BaseChannel.MessageTypeFilter, String, List, boolean, boolean, BaseChannel.GetMessagesHandler)` |



## v3.0.10

### Methods

| Old class      | Old method                                                   | New class      | New method                |
| -------------- | ------------------------------------------------------------ | -------------- | ------------------------- |
| `GroupChannel` | `void getPushPreference(GroupChannelGetPushPreferenceHandler)` | `GroupChannel` | `boolean isPushEnabled()` |

### Classes

| Old class                                           | new class |
| --------------------------------------------------- | --------- |
| `GroupChannel#GroupChannelGetPushPreferenceHandler` |           |



## v3.0.9

### Methods

| Old class               | Old method                                     | New class               | New method                                                   |
| ----------------------- | ---------------------------------------------- | ----------------------- | ------------------------------------------------------------ |
| `GroupChannelListQuery` | `void setUserIdsFilter(List<String>, boolean)` | `GroupChannelListQuery` | `setUserIdsIncludeFilter(List, QueryType) ` and `setUserIdsExactFilter(List)` |



## v3.0.2

### Methods

| Old class  | Old method                                                   | New class  | New method                                                   |
| ---------- | ------------------------------------------------------------ | ---------- | ------------------------------------------------------------ |
| `SendBird` | `static void registerPushTokenForCurrentUser(String, RegisterPushTokenHandler)` | `SendBird` | `static void registerPushTokenForCurrentUser(String, RegisterPushTokenWithStatusHandler)` |

### Classes

| Old class                           | new class                                     |
| ----------------------------------- | --------------------------------------------- |
| `SendBird#RegisterPushTokenHandler` | `SendBird#RegisterPushTokenWithStatusHandler` |

