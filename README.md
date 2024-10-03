# IMAGE-TO-SIGNAL PROGRAM
## Introduction / Method - turning images into sound
This MATLAB script generates a digital (time-domain) signal from an image and modulates it for transmission using its signal processing library. It will ask too many questions.

By nature, MATLAB creates a pixel matrix for an image with the chroma values. With known values for desired bandwidth, sampling rate, and center frequency, we can create a signal that displays the chosen image on a spectrogram. Here, we consider the image matrix as a multi-line column vector in the frequency domain.
- We grayscale and resize the image so that it looks good in the specified bandwidth, then increase the contrast inversely and logarithmically so that it shows better on our equipment (potentially not so well in MATLAB).
- We add negative space to the signal (zeros) based on the Nyquist rate, bandwidth, and center frequency in order to properly "place" the image in the correct frequency range.
- If we consider the matrix as a signal in frequency steps with intensity values, we can convert it to time steps with frequency values by utilizing the inverse FFT filter, with a few intermediate steps.

The signal outputs itself into a .txt file in a folder labeled "output," created in the same folder that the script runs. I recommend smaller image sizes to cut back on the time it takes to process (and transmit) the signal.

## Example Use
### Chosen Image (Frog with a Baguette that I drew in May)
![frog](https://github.com/user-attachments/assets/3d0b2e53-5105-4766-acfc-479b9c2d4ccf)

### Program Run
![image](https://github.com/user-attachments/assets/9697719b-2b0f-4ae1-877a-0713128903b9)

### MATLAB Spectrogram Created from the Generated Signal
![frogfroog](https://github.com/user-attachments/assets/d55baa66-f168-4cdd-9482-0a8495b16643)

### Transmission/Reception of Signal in Underwater Acoustics Lake Test
![image](https://github.com/user-attachments/assets/8aae262e-1c62-45cf-95c0-0d153d2f867c)

This image is from a lake test that occured on Aug 6, 2024 recorded by our monitor hydrophone. Since this test, I have flipped the image so that the picture is facing the "right way", as well as inverted the frequency in order to show truer color values on our specific equipment -- here, it is not inversed and flipped.

You may notice a lot of noise bleeding into the adjacent frequency ranges -- this is primarily the signal echoing off of the side of our boat and right back to the hydrophone. Our transducer and monitor hydrophone were only a few feet apart, as the transmission was meant for an AUV 300 ft away.

## Benefits of Transmitting Frogs for Science?
- Cute
- Shows fish what the frogs look like
- Educates native algae on the delights of bread
- Learn how to operate the modem from the beginning of the modulation process to the transmission in the field
- Image turned into sound!! Cool!!

## Licensing?
Do whatever you want.
