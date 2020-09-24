# Administration resources
> #### In this article, we will dig into the administrative settings of **on_board**.

## Settings

### Contact Information
> #### The contact information is used by students, as a via of communication with a support team, or advisor(s) in charge of monitoring the orientation process.

To add your contact information:
1. Go to Settings.
2. On the **Institution** section add:
  - Institution Name
  - Contact Phone
  - Contact Email
  - Postal Address *(optional)*
3. Click the **Save** button to save the changes.

### Allowed Domains
> ##### This feature allows administrators to have a better control of what email domains are being used for account creation. When enabled, only email addresses using the listed domains will be authorized by the software.

To enable this feature:
1. Go to Settings.
2. In the **Allowed Domains** section, enter the domain(s) intended to be authorized.
 - You can add multiple domains at once, separating them by comma.
3. When you are done adding the domains, click **Save** to save the changes.

### Front Page
> ##### The Front Page setting enables administrators an easy way to add a custom designed front page to ON_BOARD.

To activate this feature, simply go to Settings, add your html code into the **Front Page** section, then click **Save**.
- **Note:** ON_BOARD uses Bootstrap 4 by default, which could come handy for designers, to get a front page design ready in no time.


<hr>

# Orientations
> ##### Orientations is what ON_BOARD is about. It provides students with an easy eay of completing their orientations, and to sign any documents they need to, at their own pace. In this section you will learn how to create and manage orientations, enroll students, link documents, and more.

### Creating an orientation

To create an orientation, go to Home on your sidebar menu.
1. Click **New**, on the right side of the content area.
2. Type in the orientation name, description, and the language, then click **Save**.
  - The language field is purely informative, and it doesn't affect the orientation in terms of language or translation.

### Adding Sections

Once the orientation is created, you will be automatically redirected to the orientation content area.

To begin adding content to your orientation:

1. Click the **Add section** button, located on the right side of the content area.
2. Select the **content type** by using the dropdown menu on the right side of the content area, then click **Select**.

  #### Content Types:

  - **Text/Html**: Supports html formatted information, and utilizes a rich-text editor that allows for eady content editing right on the browser.
    - Required fields: Section label, and Description.
  - **Multimedia**: Currently supports videos hosted on Vimeo and Youtube. It takes the video's full url and plays it within the orientation.
    - Required fields: Title, URL Provider and Video.
  - **Assessment**: Allows administrators to insert single question assessments as part of the orientation experience. It currently supports multiple choice questions.
    - Required fields: Section label, Question text, and Option 1 & 2.

3. Once you are done adding a section, click **Save**.
4. Repeat the same steps to add more sections.

### Orientation Settings

> ##### We mentioned above that creating the orientation only takes a few seconds, but that doesn't mean you cannot tweak things around. We have provided some basic configuration options so that you can personalize each individual orientation and make it appeal to your institution's colors and design.

1. While on the Home screen, click on the **Settings** icon (:gear:).
  - By accessing the orientation settings, you will be able to edit the orientation name, description, and language. You will also be able to add a background image that will be used as the orientation background image on the student orientation player. Additionally, you can change the navigation buttons colors to match your institution design and colors.
2. Once you are done editing, click **Save** to persist any changes.

### Certificate of Completion

> ##### A certificate of completion may be enabled in your orientation, and can be accessed by students only after they complete all sections within. Certificates must be manually enabled inside the orientation settings, and each design may be different from the rest. This gives you the flexibility to interchange the designs without affecting others.

1. To enable and edit your certificate of completion, go to the settings of the orientation you would like to enable it for.
2. In the **Certificate** content area, click the *Enable/Disable* checkmark to turn the certificate on.
  - If you wish to disable it, make sure the checkmark is disabled, then click **Save** to persist the changes.
3. Edit the certificate using the available fields, and **Save** when you are done.

  **Hint**: Click the :eye: icon next to **Certificate** to preview your changes.

### Enrolling Students and Student Progress
> ##### There are two ways you can enroll students on an orientation. You can either do it from the orientation, if the student is already registered, or by sending an invitation to the student.

#### Enrolling existing students

1. In the Home screen, click on **Enroll students**, next to the appropriate orientation.
2. Select the student(s) you would like to enroll, then click **Enroll**.

#### Enrolling students by invitation

This one is a bit more time consuming, since right now you can only enroll one student at a time. When an invite is created, the student will receive two emails. The first will prompt the student to register on the platform, and the second one will notify the student about his/her enrollment in the orientation selected when the invitation was created.

1. On the sidebar navigation menu, go to **Users**.
2. Click **Invite** to begin entering the record.
3. Type in the student legal name, working email, and (if applicable) the orientation you wish the student to be enrolled on.
4. Click **Save** to persist the changes.

  **Note**: Once the invitation is sent, the account will be marked as pending on the **Users** content area, until the user activates his/her account.

## Users Management

In **ON_BOARD**, you can manage multiple users and their roles. Currently supported roles are Administrator, Advisor, and Student. As an administrator, you have unlimited permissions throughout the entire dashboard. To view and manage users, simply go to the **Users** content area, using the navigation sidebar.

<hr>

#### Have a recommendation?

> Help us improve this documentation [here](https://github.com/elvisblanco1993/nboard-docs/pulls).