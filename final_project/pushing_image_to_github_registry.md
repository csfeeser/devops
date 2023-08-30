# Pushing a Docker Image To GitHub Container Registry (ghcr.io)

### Prerequisites
These steps assume that you have already created an image using a Dockerfile and `docker build`.

1. To make the next steps easier, let's set some environment variables. The first variable should be the name you gave your image. If you don't remember your image name type `docker image ls`.

   `student@bchd:~$` `export image_name="your-image-name"`

0. The next variable represents your image version. You can use a number like `1` or `1.0.0` or even something like `alpha`, but DO NOT use "latest" (meow).

   `student@bchd:~$` `export image_version="your-image-version"`

0. The next variable is the GitHub username of the person **who owns the GitHub repo you are using.** Do not use your own!

   `student@bchd:~$` `export project_group="owners-github-username"`

0. The last variable is the name of the repository your group is using. Be very careful to write it correctly.
   
   `student@bchd:~$` `export project_repo="your-repo-name"`

0. Using the environment variables we created above, the following command should correctly tag the image you made with the tag needed to eventually push it to GitHub. Do not edit this command.

   `student@bchd:~$` `docker tag ${image_name} ghcr.io/${project_group}/${project_repo}/${image_name}:${image_version}`

0. You now need to create a token that gives you permission to read/write/delete images on GitHub. Go to the [New personal access token (classic)](https://github.com/settings/tokens/new) page on GitHub. Be sure to check the following boxes:
   - `write:packages` - Upload packages to GitHub Package Registry
   - `read:packages` - Download packages from GitHub Package Registry
   - `delete:packages` - Delete packages from GitHub Package Registry
     
0. To get permission to  `docker login ghcr.io -u ${project_group}`
   
0. Enter your GitHub token you created earlier when prompted.

0. Push it!

   `student@bchd:~$` `docker push ghcr.io/${project_group}/${project_repo}/${image_name}:${image_version}`

0. Chances are, however, that you will only be able to use this image in environments that contain the token you've created. This is a problem if you intend to use this in a Kubernetes cluster. The simplest way to overcome it is to make the image public. The following steps are for only for group members that have admin access in your group repo.

## For Repo Owner Only: Make GitHub Container Registry Public

1. **Go to Your GitHub Dashboard**: Navigate to the main page of your GitHub repository.

2. **Packages Tab**: 
    - Click the `Packages` tab located at the top of the repository page.

3. **Select Image**:
    - Click on the name of the image that you uploaded.

4. **Package Settings**: 
    - On the right side of the screen, locate the gear icon titled "Package Settings" and click it.

5. **Danger Zone**: 
    - Scroll down to the section in red labeled as "Danger Zone."
    - Click the "Change visibility" button.

6. **Change to Public**: 
    - Select the "Public" radio button.
    - You'll be prompted to enter the name of the package for confirmation.
    - Click the button that says "I understand the consequences, change package visibility."

7. **Final Step**:
    - You should now be able to use this image anywhere you like with no tokens required. Test it by running the following command:

   `student@bchd:~$` `docker run -p 0.0.0.0:2224:2224 ghcr.io/${project_group}/${project_repo}/${image_name}:${image_version}`
