# Change Log

## Semi-Breaking Change: Very Large Bot Sharding

#### January 3, 2018

Additional sharding requirements and information for bots in over 100,000 guilds has been added. This requires a small change in numbers of shards for affected bots. See the [documentation](#DOCS_GATEWAY/sharding-for-very-large-bots) for more information.

## New Feature: Rich Presence

#### November 9, 2017

Rich Presence is now live and available for all developers! Rich Presence allows developers to closely integrate with Discord in a number of new, cool ways like:

- Showing more information about a user's current game in their profile
- Allowing users to post invitations to join their party or spectate their game in chat
- Displaying "Spectate" and "Ask to Join" buttons on users' profiles

For more information, check out our [Rich Presence site](https://discordapp.com/rich-presence). To get started on development, [read the docs](#DOCS_HOW_TO/)!

## Breaking Change: API & Gateway Below v6 Discontinued

#### October 16, 2017

[API](#DOCS_REFERENCE/api-versioning) and [Gateway](#DOCS_GATEWAY/gateway-protocol-versions) versions below v6 are now discontinued after being previously deprecated. Version 6 is now the default API and Gateway version. Attempting to use a version below 6 will result in an error.

## New Feature: Channel Categories

#### September 20, 2017

Changes have been made throughout the documentation to reflect the addition of channel categories to Discord. These includes an additional field—`parent_id`—to the base [channel](#DOCS_CHANNEL/channel-obect) object and a new [channel category example](#DOCS_CHANNEL/channel-object-example-channel-category).

## New Feature: Emoji Endpoints

#### September 10, 2017

[Emoji endpoints](#DOCS_EMOJI/emoji-resource) have been added to the API. Bots can now manage guild emojis to their robo-hearts' content!

## Breaking Change: Presence Activity Objects

#### August 16, 2017

The `type` field in the [activity object](#DOCS_GATEWAY/activity-object) for [Gateway Status Update](#DOCS_GATEWAY/update-status) and [Presence Update](#DOCS_GATEWAY/presence-update) payloads is no longer optional when the activity object is not null.

## Breaking Change: Default Channels

#### August 3, 2017

After today, we are changing how default channels function. The "default" channel for a given user is now the channel with the highest position that their permissions allow them to see. New guilds will no longer have a default channel with the same id as the guild. Existing guilds will not have their #general channel id changed. It is possible, if permissions are set in such a way, that a user will not have a default channel in a guild.

We saw a use case in many servers where the previously-default #general channel was being repurposed as an announcement-only, non-writable channel for new members by using bots to clear the entire message history. Now, that channel can simply be deleted and re-created with the desired permissions. This change also allows dynamic default channels for users based on permissions.

We are also rolling out a change in conjunction that will allow Discord to remember your last-visited channel in a guild across sessions. Newly-joined users will be directed to the guild's default channel on first join; existing members will return to whichever channel they last visited.

## New Feature: Audit Logs

#### July 24, 2017

Audit logs are here! Well, they've been here all along, but now we've got [documentation](#DOCS_AUDIT_LOG/audit-logs) about them. Check it out, but remember: with great power comes great responsibility.

## Breaking Change: Version 6

#### July 19, 2017

* [Channel](#DOCS_CHANNEL/channel-object) Object
  * `is_private` removed
  * [`type`](#DOCS_CHANNEL/channel-object-channel-types) is now an integer
  * `recipient` is now `recipients`, an array of [user](#DOCS_USER/user-object) objects
* [Message](#DOCS_CHANNEL/message-object) Object
  * [`type`](#DOCS_CHANNEL/message-object-message-types) added to support system messages
* [Status Update](#DOCS_GATEWAY/update-status-gateway-status-update-structure) Object
  * `idle_since` renamed to `since`
