## Change Log

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
