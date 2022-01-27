Sample hosted at [flutterweb-101.web.app](https://flutterweb-101.web.app/).

1. Creat a Flutter web project

```console
flutter create --platforms=web .
```

1. Create a Firebase project

   - Go to [console.firebase.google.com](https://console.firebase.google.com/)
   - Click on "Add project"
   - Follow the instructions
   - Once the project is created...

1. Enable hosting

   - Click on "Hosting" on the left navigation (on the Firebase project page)
   - Follow the instructions to install the Firebase CLI tools (if you don't
     already have them installed).
   - When running `firebase init`, choose `Hosting` and `GitHub Action deploys`.
   - When going through the configuration, set `"public"` to `build/web`.
   - Change the build command to `flutter build web`.

1. Update `.github/workflows` for Flutter

   - Update the two generated `firebase-hosting-` files to include Flutter
     setup:

   ```yaml
   steps:
      # This has to come before `flutter bulid web`
      - uses: subosito/flutter-action@v2.2.1
      with:
         # Defining the channel is optional - I'm using beta
         channel: beta
         # Setting cache is also optional, although this does speed up builds!
         cache: true
      - uses: actions/checkout@v2
   ```
