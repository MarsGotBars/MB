# MarsBar

Little try at making a (locally) functional video-compressor (and / or video-merger) so I don't have to start up HandBrake everytime or go to https://8mb.video/ (which is a great site don't get me wrong).

Currently working on the front-end bit, as this is my first time working with Vue3 (in combination with typescript) this might take me longer than I'd like it to.

This repo may or may not contain all necessary components for this project to fully function, I'll see about it sometime later, as ~~Python~~ (switched to) NodeJS might be a requirement, ~~together with some type of local database like PocketBase~~ (Most likely gonna use PlanetBase).

## Versions

### 0.0.1

First commit version
- contains some basic styling
- mostly contains JS solutions to some of the work

### 0.0.2

Vuetifying it
- Integrating some more 'vue' into it, making use of **lifecycle hooks**, **refs** and **passing props**
- Refactored previous JS solution into vue solution
- Can add files into dropzone now
- dropzone displays proper file name
- Random texts now properly display when 'upload' (upload is not functional yet) button is pressed

# Current to-do list

- [x] Create dropzone with active for drag / drop functions
- [ ] Shorten file name (but still display file format at the end)
- [ ] Add file size options
- [ ] Progress bar for upload
- [ ] Add more loading messages
- [ ] Progress bar for processing

- optional to-do's
- [ ] \(optional) Add separate tab for making video-compilations
