# Phonic Privacy Policy

_Last updated: 2026-05-05_

## Summary

Phonic is a dictation app for iPhone. It records your voice when you ask it to and converts it into text using one of three options that **you** select in Settings:

- **On-device** (default): a Whisper model running entirely on your phone via Apple's Core ML. Your audio **never leaves the device**.
- **Groq**: each recording is uploaded over HTTPS to `api.groq.com` for transcription, authenticated with the Groq API key **you** provide.
- **OpenAI**: each recording is uploaded over HTTPS to `api.openai.com` for transcription, authenticated with the OpenAI API key **you** provide.

The first time you switch to a cloud provider (Groq or OpenAI), Phonic shows an in-app confirmation explaining what is sent, where it is sent, and asks you to opt in. Until you opt in, no audio leaves your device.

The transcribed text is inserted into whatever app you are typing in. Phonic itself does not run any servers, does not store your audio, does not store transcripts, does not show ads, and does not sell or share your data with anyone other than the provider you have explicitly chosen, for the sole purpose of transcribing your speech.

## What we collect

- **Audio recordings**, only while you are actively dictating.
- **Your provider API key** (Groq or OpenAI), which you supply.
- **App settings** (default session duration, language preference, selected provider).

We do not collect: contact lists, location, browsing history, identifiers, usage analytics, crash data, advertising identifiers, or anything you type with other keyboards.

## How we use it

- **Audio** (on-device mode): processed entirely on your iPhone using Whisper running through Apple's Core ML. The model is downloaded once from HuggingFace (over HTTPS) and cached locally; no audio is sent over the network at any point.
- **Audio** (cloud modes): sent over HTTPS to the transcription provider you have selected in Settings. The endpoints used are:
  - **Groq**: `https://api.groq.com/openai/v1/audio/transcriptions`
  - **OpenAI**: `https://api.openai.com/v1/audio/transcriptions`
  Once the transcribed text is returned, the audio is discarded. We do not retain it on the device or anywhere we control.
- **API keys**: stored locally in the iOS Keychain on your device, separately for each provider. Each key is sent only to its corresponding provider in the `Authorization` header of API requests, as required by their service.
- **Settings**: stored locally on your device.

## What we do not do

- We do not sell your data.
- We do not share your data with anyone other than the cloud transcription provider (Groq or OpenAI) you have explicitly opted into in Settings, and only for the duration of a single transcription request.
- We do not show ads.
- We do not track you across other apps or websites.
- We do not log your keystrokes or read text from the apps you type in. The Phonic keyboard only writes transcribed text into the active text field via Apple's `UITextDocumentProxy.insertText` API.
- Phonic itself does not collect, store, or transmit any data to any Phonic-controlled server. Phonic has no servers.

## Custom keyboard "Allow Full Access"

iOS requires you to enable "Allow Full Access" for the Phonic keyboard. We use this permission only to:

1. Allow the keyboard to read dictation session state from a secure shared container that the main Phonic app and the keyboard both access.
2. Allow the keyboard to receive transcribed text back from the main app.

The keyboard itself does not make network calls or read your API key — all transcription requests are made by the main Phonic app.

We do not use Full Access to read text from the apps you are typing in, to log keystrokes, or for any purpose unrelated to the transcription described above.

## Third-party services

If — and only if — you have explicitly opted into a cloud provider in Settings, your dictated audio will be uploaded to that provider's transcription endpoint (over HTTPS) when you dictate. Phonic does not relay this audio through any intermediate server — the request goes directly from your iPhone to the provider's API, authenticated with the API key you have supplied.

What is sent: a short audio recording (typically 1–60 seconds of `.m4a` AAC at your microphone's native sample rate) plus the model name and optional language hint.

What is not sent: your name, contacts, location, identifiers, other apps' data, anything you type with other keyboards, or any data tied to your identity beyond what the provider can infer from your API key.

Each provider's data handling is governed by **their** own privacy policy and your account/agreement with them, which Phonic is not a party to. We use these providers' published policies as the basis for confirming your data is handled to a comparable standard.

- **Groq**: https://groq.com/privacy-policy
- **OpenAI**: https://openai.com/policies/privacy-policy

If you would rather your audio never leaves your device at all, select **On-device** in Settings — that's Phonic's default.

## Data retention

Phonic does not retain your audio or transcripts on its servers — Phonic does not have any servers. Audio is retained only in transient memory and on temporary disk storage on your device for the few seconds it takes to upload and receive a transcription, after which it is deleted.

## Children's privacy

Phonic is not directed to children under 13.

## Changes to this policy

If we change this policy, we will update the "Last updated" date and post the new version at the same URL. If a change materially affects how we handle your data, we will surface a notice inside the app.

## Contact

For questions about this policy, contact: **zugzwang74@gmail.com**
