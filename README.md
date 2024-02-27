# uploadtodrive
A GitHub action workflow to add flutter Apk to drive and share that link to mail 

# GitHub Actions Workflow: Master Release For Test

This GitHub Actions workflow automates the process of releasing a new master APK for testing purposes.

## Trigger

The workflow is triggered in the following ways:
- Manual trigger via workflow dispatch.
- Automatically on push to the master branch.

## Steps

1. **Checkout**: Checks out the repository code.
2. **Install Java**: Sets up Java with the required version.
3. **Install Flutter**: Installs Flutter with the stable channel.
4. **Flutter Setup**: Fetches dependencies and runs static code analysis.
5. **Build APK**: Builds the APK for release.
6. **Push Release to Github**: Pushes the release APK to GitHub.
7. **Upload Artifact**: Uploads the release APK as an artifact.
8. **Upload APK to Google Drive**: Uploads the release APK to Google Drive.
9. **Send mail**: Sends an email notification about the successful build.

## Inputs

- **Artifacts**: Path to the generated APK.
- **Tag**: Version tag for the release.
- **Token**: GitHub token for authentication.
- **Credentials**: Google Drive credentials for authentication.
- **Filename**: Name of the APK file.
- **FolderId**: ID of the Google Drive folder to upload to.
- **Server Address**: SMTP server address for sending emails.
- **Server Port**: SMTP server port for sending emails.
- **Username**: Email account username for authentication.
- **Password**: Email account password for authentication.
- **To**: Recipient email address.
- **From**: Sender email address.
- **Subject**: Email subject line.
- **Body**: Email body content.
- **HTML Body**: HTML formatted email body content.
- **Reply To**: Email address to reply to.
- **In Reply To**: Email address to indicate reply to.
- **Convert Markdown**: Convert email body content from Markdown to HTML.
- **Priority**: Priority level of the email.

## Configuration Details

### Upload APK to Google Drive

To configure the Google Drive upload, you need to set up a service account in Google Cloud Console and obtain the service account JSON key file. Then, add the contents of the JSON key file as a secret in your repository settings with the name `SERVICE_KEY`. Additionally, set up a folder in Google Drive where you want to upload the APK and obtain its folder ID. Add the folder ID as a secret in your repository settings with the name `FOLDER_ID`.

### Send Mail

To configure email sending, you need to set up a Gmail account for sending emails. Then, add the following secrets in your repository settings:
- `MAIL_USERNAME`: Your Gmail email address.
- `MAIL_PASSWORD`: Your Gmail app password (generate one if you have two-factor authentication enabled).
- `MAIL_TO`: Email address where you want to send the notification.

## Usage

1. Make sure you have the necessary secrets set up in your repository settings.
2. Trigger the workflow manually via the Actions tab or by pushing changes to the master branch.

## Contributors

- [Your Name or Username](link to your profile) - Role or Contribution

Feel free to contribute to this workflow by creating issues or pull requests.

