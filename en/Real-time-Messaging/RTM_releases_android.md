
---
title: Release Notes
description: 
platform: Android
updatedAt: Sun Apr 28 2019 07:40:46 GMT+0800 (CST)
---
# Release Notes
## Overview

Designed as a substitute for the legacy Agora Signaling SDK, the Agora Real-Time-Messaging SDK provides a more streamlined implementation and more stable messaging mechanism for you to quickly implement real-time messaging scenarios.

### Highlights

- Supports sending peer-to-peer or channel messages.
- Supports call invitation required in most one-to-one or one-to-many voice/video chats. 
- Supports multiple instances so that you can call multiple RTM services in one process. 
- Categorizes the error codes so that you can quickly identify the problem.

> Fore more information about the SDK features and applications, see [Product Overview](../../cn/Real-time-Messaging/RTM_releases_android.md).

## v0.9.1

v0.9.1 is released on April 4th, 2019.

### New Features

This release adds the call invitation feature, allowing you to create, send, cancel, accept, and decline a call invitation in a one-to-one or one-to-many voice/video call. 

### Improvements

- Optimizes the object relations to facilitate understanding.
- Renames some interfaces to conform to Java naming conventions. 
- Removes `ChannelMessageState` and `PeerMessageState` to simplify the process of sending a channel or peer-to-peer message. Uses `ChannelMessageError` and `PeerMessageError` instead. 
- Removes `IStateListener` for listening to message states. Uses the generic `ResultCallback` instead.

### API Changes

#### Adds

- [LocalInvitation.setContent()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_local_invitation.html#a4cec28ff6d356242329b1034c7531445): allows the caller to set the content of an outgoing call invitation.
- [LocalInvitation.getContent()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_local_invitation.html#a97294ce1b9b591f9d93e497869b1ad90): allows the caller to retrieve the content of an outgoing call invitation. 
- [LocalInvitation.getResponse()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_local_invitation.html#a268c738458538a266d440b0e281328ee): allows the caller to retrieve the response set by the callee.
- [LocalInvitation.getState()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_local_invitation.html#a59608fbac8050f17ec0f855f28598d20): allows the caller to retrieve the state of an outgoing call invitation. 
- [RemoteInvitation.getCallerId()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_remote_invitation.html#ae38c5740aa9edb09749f0febb2663926): allows the callee to retrieve the user ID of the caller.
- [RemoteInvitation.getContent()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_remote_invitation.html#aeca3b3e981c69c44c7a618d4fdfb3b87): allows the callee to retrieve the content set by the caller. 
- [RemoteInvitation.setResponse()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_remote_invitation.html#a229b8cf773eaa0e79b0d67815fd6b6f1): allows the callee to set the response to the caller. 
- [RemoteInvitation.getResponse()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_remote_invitation.html#a12a70e7d8a77eee21d37bbb65b2f9d3e): allows the callee to retrieve the response to the caller.
- [RemoteInvitation.getState()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_remote_invitation.html#af77a4afabb19ff1468edf29720361a0f): allows the callee to retrieve the state of the incoming call invitation
- [RtmCallEventListener.onLocalInvitationReceivedByPeer()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_call_event_listener.html#a24e1cb71d3e752963da49bdf91847788): occurs when the callee receives the call invitation. 
- [RtmCallEventListener.onLocalInvitationAccepted()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_call_event_listener.html#a4dece02a62a187a66c2415fecf6b75dc): occurs when the callee accepts the call invitation. 
- [RtmCallEventListener.onLocalInvitationRefused()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_call_event_listener.html#a6224643c400268d356cb5d489825bdd0): occurs when the callee declines the call invitation. 
- [RtmCallEventListener.onLocalInvitationCanceled()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_call_event_listener.html#ae3164e81772cd4d6171165b1705adcaa): occurs when the caller cancels the call invitation. 
- [RtmCallEventListener.onLocalInvitationFailure()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_call_event_listener.html#acfefb97eaca497cbd71a0c1cbf5067b0): occurs when the outgoing call invitation fails. 
- [RtmCallEventListener.onRemoteInvitationReceived()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_call_event_listener.html#a8d01498a993c4016aa45ccb9bf4e9097): occurs when the callee receives a call invitation. 
- [RtmCallEventListener.onRemoteInvitationAccepted()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_call_event_listener.html#a81d9d3de89d08c41408d8a94c8309d29): occurs when the callee accepts a call invitation. 
- [RtmCallEventListener.onRemoteInvitationRefused()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_call_event_listener.html#a7a21eaa9ff49bcf39e3c49b94f6e6ac7): occurs when the callee declines a call invitation. 
- [RtmCallEventListener.onRemoteInvitationCanceled()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_call_event_listener.html#a9d0409c87455d4d2b1315f67a5f7aa12): occurs when the caller cancels the call invitation. 
- [RtmCallEventListener.onRemoteInvitationFailure()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_call_event_listener.html#a6f9f2bbbfbcb0a766c6f1b2e4a8314a1): occurs when the incoming call invitation fails. 
- [RtmCallManager.setEventListener()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/classio_1_1agora_1_1rtm_1_1_rtm_call_manager.html#a934eee4922584707a1a7ef9ac6999cf2): sets the event listener to the `RtmCallManager` instance. 
- [RtmCallManager.createLocalInvitation()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/classio_1_1agora_1_1rtm_1_1_rtm_call_manager.html#a1756dca077267acaa407c6901daa2248): creates a call invitation. 
- [RtmCallManager.sendLocalInvitation()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/classio_1_1agora_1_1rtm_1_1_rtm_call_manager.html#af899697061305ca840e829b92c78e353): sends a call invitation to a specified user. 
- [RtmCallManager.acceptRemoteInvitation()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/classio_1_1agora_1_1rtm_1_1_rtm_call_manager.html#a5f6f97c84e426e2fbd8a5dda71e2fc6c): accepts an incoming call invitation. 
- [RtmCallManager.refuseRemoteInvitation()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/classio_1_1agora_1_1rtm_1_1_rtm_call_manager.html#a2ce4af944183976d18c055816f756bf6): declines an incoming call invitation. 
- [RtmCallManager.cancelLocalInvitation()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/classio_1_1agora_1_1rtm_1_1_rtm_call_manager.html#a5f03bfe1cfd6987fbc7b5a4dc484f564): allows the caller to cancel an outgoing call invitation. 
- [RtmStatusCode#LocalInvitationState](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_status_code_1_1_local_invitation_state.html): states of an outgoing call invitation.
- [RtmStatusCode#RemoteInvitationState](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_status_code_1_1_remote_invitation_state.html): states of an incoming call invitation. 
- [RtmStatusCode#LocalInvitationError](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_status_code_1_1_local_invitation_error.html): error codes of an outgoing call invitation. 
- [RtmStatusCode#RemoteInvitationError](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_status_code_1_1_remote_invitation_error.html): error codes of an incoming call invitation. 
- [RtmStatusCode#InvitationApiCallError](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_status_code_1_1_invitation_api_call_error.html): error codes of the invitation-specific API calls. 
- [ConnectionChangeReason#CONNECTION_CHANGE_REASON_REMOTE_LOGIN](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_status_code_1_1_connection_change_reason.html): another instance has logged in the Agora RTM system with the same user ID. 

#### Renames

- The `RtmClient.destroy()` method, which releases all resources used by the `RtmClient` instance, to: [RtmClient.release()](../../API%20Reference/RTM_java/classio_1_1agora_1_1rtm_1_1_rtm_client.html.md).
- The `IResultCallback` class to: [ResultCallback](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_result_callback.html)

#### Deletes

- Deletes `PEER_MESSAGE_RECEIVED_BY_SERVER` from [PeerMessageError](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_status_code_1_1_peer_message_error.html), uses `PEER_MESSAGE_ERR_OK` instead.
- Deletes `CHANNEL_MESSAGE_RECEIVED_BY_SERVER` from [ChannelMessageError](../../API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_status_code_1_1_channel_message_error.html.md), uses `CHANNEL_MESSAGE_OK` instead.
- Deletes the `PeerMessageState` interface, uses [PeerMessageError](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_status_code_1_1_peer_message_error.html) instead. 
- Deletes the `ChannelMessageState` interface, uses [ChannelMessageError](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_rtm_status_code_1_1_channel_message_error.html) instead.
- Deletes the `IStateListener` class for listening to message states, uses the [ResultCallback](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_result_callback.html) class instead for listening to the peer or channel message results.
  - Success: the SDK returns the [ResultCallback.onSuccess()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_result_callback.html#a7206b30500655c4a73d146acf50cb6f5) callback.
  - Failure: the SDK returns the [ResultCallback.onFailure()](https://docs.agora.io/en/Real-time-Messaging/API%20Reference/RTM_java/interfaceio_1_1agora_1_1rtm_1_1_result_callback.html#a1f9145a3eb119e32cfc0afa938062396) callback with the corresponding error codes.

## v0.9.0

v0.9.0 is released on February 4th, 2019.

Initial version. 

Key features:

- Sends or receives peer-to-peer messages.
- Joins or leaves a channel.
- Sends or receives channel messages.
