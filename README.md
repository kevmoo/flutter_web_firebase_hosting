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
