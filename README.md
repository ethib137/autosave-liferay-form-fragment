# Autosave for Liferay Forms `7.2`

OOTB Liferay forms autosaves a form entry draft every 60 seconds for logged in users. This module seeks to improve on this functionality by saving whenever the user input changes and by letting the user know when their input is being saved.

## Usage

After deploying the module, create a new form. As a logged in user start filling out the form and you will see that a draft of the form response is being saved whenever you change the input.

## How to Build and Deploy to Liferay

### Build it
` $ ./gradlew build `
The jar file will be in `autosave.liferay.form.fragment-1.0.0.jar`.

### Deploy to Liferay
` $ ./gradlew deploy -Pauto.deploy.dir="/path/to/liferay/deploy"`

### Debugging

For a fragment to be applied it requires that you indicate the correct module and version to override in the bnd.bnd file.

`Fragment-Host: com.liferay.dynamic.data.mapping.form.web;bundle-version="2.0.42"`

If the module is not being applied to your instance as expected check which version of the fragment host is deployed by running the following command in your gogo shell.

`lb com.liferay.dynamic.data.mapping.form.web;bundle-version`

Update the bnd.bnd with the correct version and deploy the updated module.

## Issues & Questions Welcome