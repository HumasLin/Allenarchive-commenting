# Allenarchive-commenting
Commenting Plugin
Plugin files:
In /src folder. 

Before upload the files to modify the commenting function on our website, we need to do two configurations:

First, activate the ‘Commenting’ in ‘Plugins’ as a Omeka Admin, then modify the configuration by checking ‘Allows everyone, including non-registered users to comment. Using this without Akismet is strongly discouraged.’ Option to allow everyone to leave comments. However, anyone except the admin should register an account to comment since the unregistered users cannot pass Captcha to comment.

Second, set up Captcha according to the tutorial on this website, to make sure registration can work:
https://omeka.org/classic/docs/Admin/Settings/ReCaptcha/

Then, upload the source files needed for implement sentiment analysis in the plugin

There are 4 parts we need to upload to the server:
(use my address as a reference, can be replaced by other server address)

Comment section appearance:

scp /path/to/comment.php hlin374@allenarchive-hl.iac.gatech.edu:/var/www/omeka-2.7/plugins/Commenting/views/public
    
scp /path/to/commenting.css hlin374@allenarchive-hl.iac.gatech.edu:/var/www/omeka-2.7/plugins/Commenting/views/public/css

Comment database setting:

    scp /path/to/CommentingPlugin.php hlin374@allenarchive-hl.iac.gatech.edu:/var/www/omeka-2.7/plugins/Commenting
    
Controller of Comments:

    scp /path/to/controllers.zip hlin374@allenarchive-hl.iac.gatech.edu:/var/www/omeka-2.7/plugins/Commenting
    
Then: 
    
    -ssh hlin374@allenarchive-hl.iac.gatech.edu

    -cd /var/www/omeka-2.7/plugins/Commenting
    
    -sudo chown -R hlin374 /var/www/html/plugins/Commenting
    
    -unzip controllers.zip
    
    -A (replace all)
    
Controller of the setting of the Commenting box:

    scp /path/to/CommentForm.php hlin374@allenarchive-hl.iac.gatech.edu:/var/www/omeka-2.7/plugins/Commenting


With this all set up, registered users can write comments, and admins call see each comment’s sentiment score after signing in:

By clicking ‘show sentiment’, we can make the sentiment scores show, and the children nodes will follow the parent node:

<p align="center">
  <img src="https://github.com/HumasLin/Allenarchive-commenting/blob/master/images/image1.png" width="350" title="hover text">
</p>

And we can also click again to hide it.

<p align="center">
  <img src="https://github.com/HumasLin/Allenarchive-commenting/blob/master/images/image2.png" width="350" title="hover text">
</p>
