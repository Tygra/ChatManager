# ChatManager

## Permissions:

chatmanager.manage
- This permission will allow you to manage the filter dictionary.

chatmanager.ignore.chatfilter
- This permission will give you the ability to ignore the chat filter.

chatmanager.ignore.spamfilter
- This permission will give you the ability to ignore the spam timer.

## Supported exceptions:

A maximum of 20 characters are allowed in a name.

A maximum of (configurable) spacekeys are allowed in a name.

Only alphanumeric characters are allowed in a name, this can be dis- and enabled through config.

All items in the base filters are disallowed by default, you can make this offense banable by bool.

All items in the base filters are filtered out in chat. This does **NOT** remove the message, instead it replaces the word with a set of '***'

Limits messages to 1 per (configurable) amount of seconds. This prevents spam & inconvenient chat abuse.

All exception reasons are configurable.

## Config options:

```csharp
		// Activate Username validation
		public bool ApplyNameValidator;

		// Checks to ban or disconnect joining users
		public bool BanIfInappropriateUsername;

		// Checks to allow nonalphanumeric characters in
		public bool CheckForAlphaNumInUsername;

		// Checks to allow spacekeys in names
		public bool CheckMaxSpacesInUsername;

		// Amount of space keys to allow
		public int MaxSpacesInUsername;

		// Activate Chat filter
		public bool ApplyChatFilter;

		// Speed in which messages are sent in chat.
		public int MsgSpamIntervalInSec;

    ...

    DisconnectReasons = new Dictionary<string, string>
      {
      // The max char amount kick reason.
        { "MaxLengthReason", "Your name is too long. Please rejoin with a shorter name. Maximum amount of characters is 20." },

      // The max spaces amount kick reason (reuse the {amountofspaces} tag to replace this value with the MaxSpacesInUsername value).
        { "MaxSpacesReason", "You have too many spaces in your name. The maximum allowed is {amountofspaces}. Please rejoin with a shorter name." },

      // The inappropriate name kick/ban reason (change this to fit your preference for banning or kicking).
        { "InappNameReason", "Inappropriate names are not allowed. Please rejoin with a tolerable name." },

      // The non-alphanumeric name kick reason.
        { "NonAlphaNumReason", "Foreign characters in your username are now allowed. Please rejoin with only alphanumeric characters." },

      // The sending-messages-too-fast reason in chat.
        { "SpamMessageReason", "You are sending messages too fast. Please slow down." }
      }
```

## Command:

/managefilter (or /mf) help/add/del/list

## Additional function:

You can easily use colors in chat by applying the following parameters:

@red/green/blue/yellow/cyan/purple/pink: MESSAGE \

Example:

`I am writing @red:a red message to display\ in chat.`
