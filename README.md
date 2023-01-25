# VSCode Jupyter Remote Server
This notebook starts a private remote Jupyter notebook sever that you can connect to using VSCode's remote kernel mode.

## Overview
This notebook downloads and runs [NGrok](https://ngrok.com) to create a reverse tunnel to the Jupyter notebook server running 'locally' on Kaggle.

Because this method bypasses Jupyter's authentication, use protect the NGrok tunnel with a username and password.

## Setup

### NGrok
This notebook using [NGrok](https://ngrok.com/) to create a 'reverse tunnel'. Sign up for a free account, and make a note of your `auth token`

### Secrets
If running this on [Kaggle](https://www.kaggle.com/), this notebook uses 'Kaggle Secrets' so your auth token isn't stored in the notebook or viewable by others.
On the Kaggle notebook editor page, click on 'Add-Ons', then 'Secrets'. Create 3 secrets:
 * `NGROK-AUTH-TOKEN` - Your Auth token from the NGrok dashboard
 * `NGROK-USERNAME` - The username for the tunnel's HTTP authentication
 * `NGROK-PASSWORD` - The username for the tunnel's HTTP authentication
 
 If not on Kaggle, the code will look for those values in the program's Environment Variables.
 
 To run the tunnel without a username or password, set the `NGROK-UNSAFE-NO-PASSWORD` secret/env variable.

  **-------------------------------**
  
  **NOTE** running without a username and password is unsafe - NGrok URLs are only obfuscated, mean they can discovered by strangers who can then
 connect into your notebook environment and **RUN ARBITRARY CODE** inside it. Only use this when you really know what you're doing
 
  **-------------------------------**
