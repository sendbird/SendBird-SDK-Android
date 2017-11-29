## Change Log

### v3.0.44(Nov 29, 2017)
* Modified init() method.

### v3.0.43(Nov 25, 2017)
* Stabilized to support Android O. 

### v3.0.42(Nov 13, 2017)
* Fixed GroupChannel isHidden() bug.

### v3.0.41(Nov 10, 2017)
* Added onChannelHidden() to ChannelHandler.

### v3.0.40(Nov 9, 2017)
* Fixed bugs handler for connect is not called when the application becomes foreground.

### v3.0.39(Nov 8, 2017)
* Added isHidden() to GroupChannel.
* Stabilized connection.

### v3.0.38(Sep 1, 2017)
* Fixed occasional crash on blocking or unblocking users. 

### v3.0.37(Aug 29, 2017)
* Added getChannelCount to GroupChannel.
* Added resetMyHistory to GroupChannel not to load messages created before the reset.
* Added network detection and auto reconnect when the network is detected. (SendBird.setNetworkAwarenessReconnection is provided to enable this option - default true)

### v3.0.36(Aug 21, 2017)
* Added isBlockedByMe and isBlockingMe flag to group channel members.
* Added getMessageChangeLogsByToken to channel to track updated or deleted messages.

### v3.0.35(Aug 18, 2017)
* Added new group channel hide to give you change to select whether channel member can load previous messages when the channel reappears.
* Added user MetaData feature.
* Added freeze status flag to open channel.

### v3.0.34(Aug 12, 2017)
* Added ChannelHandler callback on MetaData and MetaCounters creation, update and deletion.
* Added channel name filter for GroupChannelListQuery.
* Added getInviter() to GroupChannel.

### v3.0.33(Jul 24, 2017)
* Minor bug fixes. 

### v3.0.32(Jul 20, 2017)
* No more crash when profile image with special characters in the file name is uploaded. 

### v3.0.31(Jul 15, 2017)
* Added messaging copy from one channel to other channels (Sender must be a member or participant of the channels).

### v3.0.30(Jul 10, 2017)
* Support users to accept or decline other users' invitation to a group channel.
* Added group channel join preference for accepting invitation automatically.
* **Notice**: From this version, the return type of GroupChannel methods previously returning `List<User>`
such as GroupChannel.getMembers, GroupChannel.getTypingMembers and etc. now return `List<Member>`.

### v3.0.29(Jul 4, 2017)
* Added feature to set and get push notification sound for the logged-in user.

### v3.0.28(Jun 20, 2017)
* Fixed bug BaseMessage.buildFromSerializedData incurring crash for messages serialized by versions prior to v3.0.27.

### v3.0.27(Jun 15, 2017)
* Added custom type filter to OpenChannelListQuery and GroupChannelListQuery.
* Added messaging editing feature.
* Added file uploading cancel.

### v3.0.26(May 19, 2017)
* Added OpenChannel deletion. 

### v3.0.25(May 9, 2017)
* Fixed custom host bug.

### v3.0.24(Apr 19, 2017)
* Added connect() custom host feature.

### v3.0.23(Apr 12, 2017)
* Added real size property for generated thumbnails.
* Added progress handler for file uploading.
* Support file uploading on background.

### v3.0.22(Mar 9, 2017)
* Fixed bug GroupChannel.getUnreadMessageCount() returning wrong value not covered on v3.0.20.

### v3.0.21(Mar 8, 2017)
* Added getTotalUnreadChannelCount() to GroupChannel to enable you get channel count of having unread messages.
* Fixed getTotalUnreadMessageCount() to return correct value when it is called in ChannelHandler.onChannelChanged after markAsRead() is called.

### v3.0.20(Mar 6, 2017)
* Added getting messages methods to BaseChannel and they support type/customType filtering.
* Added option for using channel member's profile URL and nickname as message sender's.
* Support updating channel member's profile URL and nickname automatically.
* Fixed bug GroupChannel.getUnreadMessageCount() not returning correct value.

### v3.0.19(Mar 2, 2017)
* Added file encryption and access control feature.
* Provide serialization/deserialization for user, channel and message objects for developers to take advantage of their own local cache.
* Sender is excluded from read receipt.

### v3.0.18(Feb 22, 2017)
* Fixed bug GroupChannel.getReadReceipt() always returning the count of members of the channel after the first connection.
* From now, empty string as user ID is not accepted.

### v3.0.17(Feb 10, 2017)
* Fixed bug calling ChannelHandler.onReadReceiptUpdated() even when markAsRead() is called from the same user connected on other devices.
* Improved stability by removing occasional NPE crash on connection or reconnection.

### v3.0.16(Jan 31, 2017)
* Added reconnect() to support explicit reconnection process.
* Added removeAllConnectionHandlers() and removeAllChannelHandlers().
* Improved network call performance after reconnection is established.
* Fixed bug removing connection handlers and channel handlers when disconnect() is called.
* Improved stability.

### v3.0.15(Jan 18, 2017)
* Fixed bugs returning wrong unread count of messages when users are invited to GroupChannel.
* Fixed bugs occurring occasional crash when getReadReceipt(), getReadMembers() or etc are called.

### v3.0.14(Jan 4, 2017)
* Added thumbnail generating option when image file is uploaded.

### v3.0.13(Jan 3, 2017)
* Changed connection protocol to avoid connection reset which can occur when application runs behind proxy.

### v3.0.12(Dec 23, 2016)
* Added push notification template option, which gives option to users the way to display push notification messages.
* Improved to try connection without delay when reconnection is needed.

### v3.0.11(Dec 16, 2016)
* Added unique push token registration option, which makes sure to maintain only one GCM/FCM token for the current user.

### v3.0.10(Dec 7, 2016)
* Added GroupChannel.isPushEnabled() to check push preference for each group channel.
* Deprecated GroupChannel.getPushPreference().
* Fixed randomly occurring NPE crash when user join event or read receipt update event happen.
* Improved stability.

### v3.0.9(Nov 30, 2016)
* Added user IDs filters and query type to GroupChannelListQuery.
* Added channel custom type for OpenChannel and GroupChannel.
* Fixed to call ChannelHandler.onChannelChanged when unread message count or last message has been updated.

### v3.0.8(Nov 23, 2016)
* Fixed to update last message of group channel when UserMessage or FileMessage is successfully sent.
* Improved stability.

### v3.0.7(Nov 4, 2016)
* Fixed connection bug.

### v3.0.6(Nov 3, 2016)
* Added group channel list search by a member nickname. (Search by multiple nicknames option in v3.0.5 is no more supported.)
* Added auto-translating feature to UserMessage.
* Improved connection performance.
* Improved stability.

### v3.0.5(Oct 31, 2016)
* Added custom type to messages.
* Added group channel list search by member nicknames and user IDs.
* Added creating and updating channel cover image with binary file.
  
### v3.0.4(Sep 30, 2016)
* Fixed file uploading timeout.

### v3.0.3(Sep 27, 2016)
* Supports Android 7.0 (Nougat) and FCM.
* Fixed to increase unread message count only for others' message reception.
* Improved performance and stability.

### v3.0.2(Sep 6, 2016)
* Added features like filtered user list, open channel keyword search, push preference setting, etc.
* Added auto background detection.
* Improved stability.

### v3.0.1(Sep 1, 2016)
* Fixed minor bugs.

### v3.0.0(Aug 12, 2016)
* First release.
