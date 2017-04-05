# Configuration 

### Site Title

After installing IdeaSpaceVR, navigate to `Settings` and `General`. There you can enter your `Site Title` as well as select the preferred user interface language. 

### Origin Trial Token for Chrome

If you navigate to `Settings` and `General` you will find a so-called Origin Trial Token text input field. Since WebVR is still an experimental feature in most web browsers, the Google Chrome team decided that if you want to offer WebVR content to your website visitors, you have to include a meta tag in your website which shows virtual reality content. This meta tag will automatically enable WebVR in the web browser and your content can be rendered. This meta tag is just used for Google Chrome and will become obsolete after WebVR is officially available. 

#### Follow these steps in order to setup your personal Origin Trial Token

1. Navigate to the Origin Trials Token Sign Up page: https://docs.google.com/forms/d/e/1FAIpQLSfO0_ptFl8r8G0UFhT0xhV17eabG-erUWBDiKSRDTqEZ_9ULQ/viewform 

2. Fill out the form and submit it.

3. Once you received your Origin Trial Token by e-mail, login to your IdeaSpaceVR installation, navigate to `Settings` and `General`, enter your token code and save it. The meta tag including the token code will be added to all your WebVR pages (spaces). 


### Dashboard: Memory Limit

On your dashboard you find a section called `At a Glance`. In there you find important information about your server setup. This settings determine wether your IdeaSpaceVR setup can work properly. The most important parameter is `Memory Limit`. If this value is too low (`< 128M`) you will run into problems when uploading high resolution photo sphere images: low memory makes server-side processing of high resolution images impossible (for example creating a thumbnail image from a photo sphere image). Ideally, this value is set to `256M` or higher in your `php.ini` file. 
