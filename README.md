# Expo Constants.deviceName returns null or empty string on Android emulators

This repository demonstrates a bug where `Constants.deviceName` from Expo unexpectedly returns `null` or an empty string on Android emulators. This inconsistency can disrupt app functionality that relies on device name identification.

## Bug Description
The `Constants.deviceName` API, expected to provide the device's name, occasionally returns an empty string or `null`, specifically when running on Android emulators. This behavior is not consistent; it doesn't occur every time the app runs.

## Steps to Reproduce
1. Clone this repository.
2. Run the app on an Android emulator using Expo Go.
3. Observe the console output; `Constants.deviceName` may return `null` or an empty string.

## Expected Behavior
The API should consistently return the name of the Android emulator device.

## Actual Behavior
The API returns `null` or an empty string in an intermittent and unpredictable manner.

## Solution
The solution involves using a fallback mechanism, providing a default value if `Constants.deviceName` fails to return a valid name.  See the provided `bugSolution.js` for a practical implementation. This ensures that the app doesn't crash or exhibit unexpected behavior due to this API inconsistency.