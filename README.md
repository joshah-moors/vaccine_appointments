# Vaccine Appointments
Automatically searching for vaccine appointments

## https://joshah-moors.github.io/vaccine_appointments/

This fork of the repo includes a page with the original author's Python code ported to Javascript.
The goal here is to make the tool accessible to people without having to download and run the Python script.

One consideration is that with a browser-based app, I have to use a CORS-proxy to fetch the data on-page.
During development I observed what seemed like some kind of cache implemented at the proxy that was returning stale data.
I switched from `api.allorigins` to `api.codetabs` for the proxy and have not seen the issue since - still something to be watchful for.

# Usage

To copy this package, run:

`git clone https://github.com/TheIronicCurtain/vaccine_apointments`

## Texas

### On Windows

Download the file `dist/texas.exe`, it's an executable file that can run directly on your machine. If you want to restrict the cities open your command line (by searching cmd) and type the path to `texas.exe` followed by the cities you want, like I explained in the Python version below.

### Using Python

Run the following in the command line:

` python texas.py [cities] `

Where `cities` are the cities you want to restrict your search to. If none are provided it will open all available appointments. e.g. if you're in the San Antonio area you might put: 

`python texas.py "San Antonio" Jourdanton Pleasanton Leming Poteet`

Once it starts running, it will ping HEB periodically until an appointment in one of those cities shows up, and then open it in your web browser. You still have to be quick from there!

The loop will stop running once it finds a page to open, so if you don't get the appointment on the first try just run it again!
