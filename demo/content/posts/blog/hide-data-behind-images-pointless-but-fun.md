---
title: Hide Data Behind Images, Pointless but fun
path: /hide-data-behind-images
tags:
  - Cyber Security
metaImage: assets/hide.jpg
featuredImage: ./assets/hide.jpg
excerpt: Steganography is the art of hiding messages in such a way that no one,
  apart from the sender and receiver, suspects the existence of the hidden data.
  In this tutorial, you’ll learn a neat trick using which you can hide
created: 2020-07-19T16:54:51.467Z
updated: 2020-07-19T16:54:51.530Z
---
Steganography is the art of hiding messages in such a way that no one, apart from the sender and receiver, suspects the existence of the hidden data. In this tutorial, you’ll learn a neat trick using which you can hide whatever data you want behind an image of your choice.

## How to hide data inside images?

1. Create a folder. Name it anything you wish, say `hide`.
2. Now put anything and everything you want to hide in this folder. Text files, other images, executables - anything. Also, put the image behind which you want to hide the files in the same directory, say “image.jpg”.
3. Now we need to archive this folder. You can use your choice of compression tool for this (I recommend the free and open source [7-zip](http://www.7-zip.org/)). So now we have `hide.zip` containing all of the data we want to hide behind an image.
4. You should have your image, say `image.jpg` (inside of which we’ll hide our data) in the same directory as `hide.zip` (next to it).
5. Now simply open up the command prompt and move to the folder where `image.jpg` and `hide.zip` are located using the `cd` command:

   ```shell
   cd PATH
   ```

   For example:

   ```shell
   cd C:\Folder
   cd desktop
   ```
6. Now we type in the following command:

   ```powershell
   copy /b image.jpg + hide.zip output.jpg
   ```

After running this command, you should see an `output.jpg` in the folder and if you look closely, you’ll notice that it’s size has increased by approximately the size of the archive. Our data is now **hidden behind the image**.

The newly created `output.jpg` behaves like a normal image file, but you can also view the hidden data by opening the file with your compression tool, say 7-zip (Right click -> Open with -> 7-zip).

---

And that’s It! Now you can send this image to anyone, what others will see is just a regular image but if the recipient knows, they will be able to access the secret information privately. You can also do this for other file types as well such as .mp3, .wmv, .txt, etc.

Of course, this is just a little trick and not a substitute for proper encryption (it could be if you added a password to your archive file). Still, it isn’t exactly subtle if you hide tens or hundreds of megabytes of data behind an innocent image file, which is why you should use proper encryption tools such as [veracrypt](https://veracrypt.codeplex.com/) if you have some important or confidential data that you wish to keep hidden.