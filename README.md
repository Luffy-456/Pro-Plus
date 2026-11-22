# Activity Pro+

Activity is an offline Android camera and screen-recording app based on FadCam.
This Pro+ build removes app-level Internet/network permissions, cloud features,
and remote streaming. Recordings are saved locally on the device.

## Offline behavior

- The merged app manifest removes `INTERNET`, `ACCESS_NETWORK_STATE`, and
  `ACCESS_WIFI_STATE`, including declarations added by dependencies.
- Remote camera streaming, cloud account access, in-app update checks, weather
  lookups, and reverse geocoding are unavailable.
- Location watermarks can show device coordinates; a system location provider
  may determine location according to Android's device settings.

## Build locally

Install the Android SDK and Java 17, then run:

```shell
./gradlew assembleDefaultProPlus
```

The APK is written under `app/build/outputs/apk/default/proPlus/`. A local
release keystore can be configured through `local.properties`; without one,
the build output is unsigned.

## GitHub Actions

Pushes to `main`, pull requests, and manual workflow dispatches run the
**Build Activity Pro+** workflow. It builds the `defaultProPlus` variant and
uploads the APK as the `activity-pro-plus-apk` artifact.

## License and acknowledgements

Activity Pro+ is derived from the FadCam project. See [LICENSE](LICENSE) and
the upstream [FadCam repository](https://github.com/anonfaded/FadCam) for
license and project information.
