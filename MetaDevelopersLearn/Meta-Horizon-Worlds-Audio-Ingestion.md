# Meta Horizon Worlds Audio Ingestion

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/help-and-reference/horizon-worlds-audio-ingestion)

For ingestion of audio from outside of the platform, Meta Horizon Worlds supports .WAV format and Ogg Opus container format. When audio assets are properly prepared, they can be uploaded to the platform through the web interface or the Desktop Editor into your Asset Library.

## Supported Formats

### .WAV

All .WAV files must be recorded and saved at 48k sampling rate. Unsupported sampling rates may cause breakages. Do not upload these assets.

| Audio type | File type | Loudness and Duration | Usage | Notes |
| --- | --- | --- | --- | --- |
| Mono | Mono 48kHz, 24-bit, .wav | -18 LUFS Maximum Peak Value: <= -1.0dBTP | Sounds effects tied to a location in the world. | Avoid including reverb or spatialization pre-baked into asset files unless for expression/flavor |
| Ambisonic | First-Order Ambisonic (FOA), 48kHz, 24-bit, .wav Looping | -40 to -30 LUFS Duration: ~30 seconds | Ambience or general four-channel first-order ambisonic | Ambisonic content should not contain too much broadband noise, which may conflict with spatialized emitters. |
| Stereo | Stereo 48kHz, 24-bit, .wav Looping | -14 to -12 LUFS Maximum Peak Value: <= -1.5dB Duration: 90–120 seconds | Headset-locked content, no spatialization. E.g. Music. | Avoid including lyrics in your music. Music provided by third-party sources may need to be edited into loops by the development team. |

### Ogg Opus

Ogg Opus is a general-purpose compression format that provides mono, stereo, and *ambisonic* sound functionality.

*   Ogg Opus is a container format for sound.

*   Ogg Opus is not supported for import into Unity.

For more information about the Ogg Opus codec, see: [https://opus-codec.org/](https://opus-codec.org/) If you want to know more about ambisonic audio, see: [https://facebookincubator.github.io/facebook-360-spatial-workstation/Documentation/SDK/Audio360\_SDK\_GettingStarted.html?highlight=channel#encoding-opus-files](https://facebookincubator.github.io/facebook-360-spatial-workstation/Documentation/SDK/Audio360_SDK_GettingStarted.html?highlight=channel#encoding-opus-files) | Audio type | File type |  | Loudness and Duration | Usage | Notes |
| --- | --- | --- | --- | --- | --- |
| Mono | 48k sampling rate Channels: 1 No bitrate restrictions | -18 LUFS Maximum Peak Value: <= -1.0dBTP | Sounds effects tied to a location in the world. | Avoid including reverb or spatialization pre-baked into asset files unless for expression/flavor |  |
| Ambisonic | First-Order Ambisonic (FOA) 48k sampling rate Channels: 4 No bitrate restrictions Looping | -40 to -30 LUFS Duration: ~30 seconds | Ambience or general four-channel first-order ambisonic | Ambisonic content should not contain too much broadband noise, which may conflict with spatialized emitters. |  |
| Stereo | 48k sampling rate Channels: 2 No bitrate restrictions Looping | -14 to -12 LUFS Maximum Peak Value: <= -1.5dB Duration: 90–120 seconds | Headset-locked content, no spatialization. E.g. Music. | Avoid including lyrics in your music. Music provided by third-party sources may need to be edited into loops by the development team. |  |

## Known limitations

*   Audio uploads under 50MB.
    
    *   Mono, Stereo, and First Order Ambisonic files are supported
    
    *   All spatial SFX should be imported as mono assets; memory is wasted if you upload stereo assets and sum them to mono in the build.
    
    *   First Order Ambisonic files must be Ambix format to ensure correct orientation.

*   Audio assets that are larger than 2.5 MB are streamed from disk.
    
    *   Only one audio asset larger than 2.5 MB should be playing at any time.

*   Stereo assets that are uploaded and summed to mono costs memory and CPU.
    
    *   Downmixing assets consumes CPU.

## Upload Audio

### Desktop Editor

*   Open a world in the Desktop Editor.

*   Click the **Asset Library tab**.

*   From the Asset Library tab, click **Add New**. Select `Audio`.

*   Navigate your local environment to select the .WAV or Ogg Opus file to upload.

*   Select the folder in your Asset Library tab where you wish to upload the asset. To share the asset with other team members, it must be uploaded or moved to a shared folder.

*   Click **Upload**.

*   Repeat the above steps for other audio files.

### Meta Horizon Worlds Creations

*   Navigate to the [Meta Horizon Worlds Creations site](https://horizon.meta.com/creator/) .

*   In the left nav bar, select **My Assets > View All**.

*   At the top right, select + **Import > Sound**. 
    
    ![Screenshot of the My Horizon Creations page showing Import button with Sound dropdown option.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/453153965_514606404410649_6610638626555006606_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=2UZoETljjsEQ7kNvwHVHmlE&_nc_oc=Adna_u5iBftSa5kMlsuMPHFdD2kldS2SdGJNuC4pq2ZX1NT3SWW9dzWzivUuMZxazV4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=sFhnHKhE-WkEkmYuppm-3w&oh=00_AfTIjgvKC2DBogIxG6lPxGVLWi6X2AHwDYfpW0a5q3-TNw&oe=689BBDF3) 

*   Follow the instructions: 
    
    ![Screenshot of the Import sound dialog box.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/453246470_514606361077320_8634362095564043733_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=Kx_MF3Y1BhUQ7kNvwFk99mE&_nc_oc=AdkwWx-pbQs4uoWi8ZYlVlsCADDbz3AoVLcb7zr2WkejD6HkV91f8BwFPU7oliDK7kk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=sFhnHKhE-WkEkmYuppm-3w&oh=00_AfRBQsuRaefY4491EXsmoCWCwWw_-0kzNxzLxo_kAqHMFw&oe=689BA632) 

*   When your audio file has been uploaded, select the context menu on the asset tile to edit, delete, or play the audio asset: 
    
    ![Asset tile showing Play option highlighted in dropdown menu.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/453091793_514606381077318_5437568068305643374_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=YmCXvSM_eVsQ7kNvwFwoNXc&_nc_oc=Adl5RVQiG1Km2v5HHn4DsYWh5Si3samnV5pI2RiGayg7GOOKRH-gc7yctAnPAhxipzk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=sFhnHKhE-WkEkmYuppm-3w&oh=00_AfRvsG6-cqgmmmS-x6-84wiXrnK0XsyC_i-R933Tb104-Q&oe=689BA4AD) 

## Edit Assets **Note**: Following steps reference editing assets through the Horizon Words Creations interface.

*   To view an asset’s details, click on the asset you uploaded to your folder. The following video demonstrates this process: 
    
    ![GIF showing clicking on an asset tile, which opens up a details dialog box showing "Description", "Tags", "Folder", "File size", "Owner", "Asset ID", and "Last edited" fields.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/453003674_514606357743987_5499500488650383560_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=1Y25hUEuLyMQ7kNvwHdatIo&_nc_oc=Adlu2MVdGJ3J3eAHUBwrOp-LHzziUqQOWk-Ur5yAV7uaEZIlRhywcVZGv3wohoLVvGQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=sFhnHKhE-WkEkmYuppm-3w&oh=00_AfQXVboSZHyUme_L07pBF_SwMcpkjKvfgN9ukL_E0b_n7g&oe=689B933F) 

*   To edit the asset, click the context menu on the asset tile, or click **Edit** in the Details view.

*   Modify the name, description, tags, folder, and associated audio file for the asset: 
    
    ![Screenshot showing the "Edit sound" dialog box with "Title", "Description", "Tags", and "Folder" fields and a drag and drop area to replace the sound file.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/453091053_514606447743978_5542190667677873274_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=yWMeceb52-IQ7kNvwGZXuoI&_nc_oc=AdlyUYcZ3NceIos8VIVyVVFtRkIzF4kHKHm6OD_BkwINhe9nA1WelLhCQusg_3BAnds&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=sFhnHKhE-WkEkmYuppm-3w&oh=00_AfQk3R0cotwO04GExJjGRfxVm4aws0D5J66q6TjyjWjNAg&oe=689B897D) **Note**: You can replace the audio assets only for assets that you own.

After the audio details are added, they are displayed:

![Screenshot showing the audio asset's details dialog box.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/453002228_514606444410645_6473498994597117976_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=6D8kvGqAAokQ7kNvwFKo1cR&_nc_oc=AdlepUWMAmfCTqlO_YIgpKWp0HejCnFOXMYdfs-pqg5tYF6-42ZRZL02rphmYav_wR0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=sFhnHKhE-WkEkmYuppm-3w&oh=00_AfSjOwzG8fjDS3-KM8d_k-VmKoJR94zGIyunxj9NwHvcJA&oe=689BB476)

## Use audio

Your new audio asset can be accessed from your Asset Library. From the Desktop Editor, you can drag the asset into your world and place it and modify its properties as needed.

### Runtime limits

*   A maximum of **1024 virtual audio sources** can be available at any one time.

*   A maximum of **64 audible sounds** can be played at any time.
    
    *   If there are more than 64 audio sources, the quietest sounds are muted to limit the number to 64.
    
    *   If enabled, player-to-player voice-over (VOIP) counts as 1 audible sound source.

### Memory usage

As soon as an audio asset is instantiated in the world, its referenced audio data is loaded into runtime memory. This applies to spawned audio or audio entities in the world at startup.

### Preview playback

To preview the audio, select it. In the Properties panel, click **Play**.

You can also preview in your headset. See the following video for a demonstration of this process:

![Screenshot of VR showing My Assets pane in the Build menu.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/453002823_514606387743984_4603528703401156022_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=eWCaXMOyi8kQ7kNvwF4Sa-u&_nc_oc=Adksc7ondwYt146_S7biFWHMHRIdU9lWWjiQWqaJ6kdd7_ryHmwa3VWLfQQLU7-0kjg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=sFhnHKhE-WkEkmYuppm-3w&oh=00_AfTYqRHh5wZYD12SLhtAsLoK0IZiEUTQ0gJFeUH4HVHryQ&oe=689BADB5)

### Audio properties

When you add a sound into your world, it is encapsulated in an Audio gizmo. Select the gizmo, and the following properties are displayed in the Properties panel:

| Property | Description |
| --- | --- |
| Preview | Use the Play and Stop buttons to preview how the sound asset is presented in the world. Make adjustments to the playback properties of the asset and then retest playing. |
| Play on Start | When enabled, the sound asset is played when the world starts. If Play on Start is disabled, you must manage the playback of this ambient asset through TypeScript. |
| Loop | When enabled, the sound asset is played repeatedly. |
| Volume | Set the volume of asset playback on a scale from 0 to 1. |
| Volume randomness | Sets the randomness of volume around the current Volume setting as the midpoint of the range. Range is 0.00 to 1.00. Example: Setting to 1.00 means that actual volume in Volume +/- 6db, which is an internal limit on randomness. |
| Pitch | You can pitch the general playback of the sound up (positive values) and down (negative values). The pitch is on a scale of -24 and 24 semitones, which is manipulated by changing the speed. 12 semitones -> 1 Octave → 2x speed |
| Pitch randomness | Sets the total range in semitones. Example: Setting this value to 4.00 means that the pitch value is selected at random in the range from (Pitch - 2 semitones) to (Pitch + 2 semitones). |
| Global | When enabled, the asset is played back without any falloff due to distance. |
| Minimum Distance | When Global is disabled, set the minimum distance that a player must be from the sound asset in order to trigger playback. Minimize the minimum and maximum distance values, where possible. |
| Maximum Distance | When Global is disabled, set the maximum distance that a player must be from the sound asset in order to trigger playback. Minimize the minimum and maximum distance values, where possible. Minimum and maximum distance are three-dimensional vector distances. |
| Low-pass cutoff | Frequency in hertz that defines the low-pass cutoff, which accentuates sounds below this frequency and attenuates sounds above it. Default is 20000 hertz. |
| Send Audio Complete | When enabled, an event is sent to all subscribers to indicate when the sound playback is complete. For ambient music, do not enable this option. |

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 