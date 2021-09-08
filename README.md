# IMAX_Doppler_Filter
A jupyter notebook to filter the LOS Doppler data of the Sun's Photosphere

Spectropolarimetric inversion of data from the Imaging Magnetograph eXperiment (IMaX) instrument (Martínez Pillet et al., 2011) on the first flight of the SUNRISE stratospheric balloon (Solanki et al., 2010) yielded two 20 – 30 minute high resolution time-series of the photospheric Doppler velocity with 33 second cadence. Two regions near solar disk center were observed with spectral resolution of 85 mÅ at a cadence of 33 seconds, one for a total of 23 minutes and the other for 32 minutes (the later is publicly available in this repository). A Milne–Eddington inversion (MILOS—Suárez et al., 2010) was used to determine the magnetic field components, line-of-sight velocity, and plasma temperature over the field of view of each image frame in the time series. Doppler data for the extended observation (32 minutes) is available to download at https://drive.google.com/file/d/1F-9S7uYgnIwpvN25HZOqY5WS_eeYH1Ab/view?usp=sharing. 

Magnetohydrodynamic simulations reveals that there should be atleast two contributions to the Doppler LOS velocity measured at any position in the solar photosphere: the convective flow (graular motion), and the acoustic modal oscillations. In this jupyter notebook, these two contributions are separated by applying a Fourier filter to the Doppler data. The image timeseries were spatially apodized using a two-dimensional cosine-bell taper of width of 10% of total pixels applied to each edge, Fourier transformed in time and space, and separated into the granular and p-mode components either side. To achieve this, 3D FFT, spatial averaging to collapse the 2D spatial dimension into 1D, k-means clustering and image filtering in FFT-space are utilized. An example of the reulsting image timeseries is given below: 

![Doppler Filter](https://user-images.githubusercontent.com/66755474/132464625-1a0741e0-c813-4367-8aa5-9144e73de2e8.png)

References:

Pillet, V. Martínez, et al. "The Imaging Magnetograph eXperiment (IMaX) for the Sunrise balloon-borne solar observatory." Solar Physics 268.1 (2011): 57-102.

Solanki, S. K., et al. "SUNRISE: instrument, mission, data, and first results." The Astrophysical Journal Letters 723.2 (2010): L127.

Suárez, D. Orozco, et al. "Retrieval of solar magnetic fields from high-spatial resolution filtergraph data: the Imaging Magnetograph eXperiment (IMaX)." Astronomy & Astrophysics 522 (2010): A101.
