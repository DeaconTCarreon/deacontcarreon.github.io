---
title: "The MAVEN Solar Energetic Particle Instrument Investigation"
excerpt: "(Spring 2026-Present). An ongoing URAP project I am undertaking with Ali Rahmati at the Space Sciences Laboratory in UC Berkeley that analyzes data from the MAVEN Spacecraft's SEP instruments. My studies include extrasolar X-rays from Scorpius X-1, an accreting Neutron Star, and predicting the incident flux from the brightest gamma-ray ever observed. (Image Credit: NASA)<br/><img src='/images/MAVEN Spacecraft.jpg'>"
collection: research
type: "research"
permalink: /research/ssl-maven
venue: "SSL"
location: "UC Berkeley"
---

<img src="/images/MAVEN Spacecraft.jpg" alt="IDL Tplot" style="display: block; margin: 0 auto; width: 100%; max-width: 1200px; border-radius: 10px; margin-bottom: 20px;">

The MAVEN spacecraft orbited Mars for 12 years from 2013 to 2025 with a mission to understand the atmospheric evolution of the planet. In December 2025, Contact was permanently lost with the spacecraft, however we stil have all of its data to analyze.

I joined this research project in Spring 2026, and I have learned how to operate IDL out of MobaXTerm, which has included tplot. Tplot is a system that allows graphing many variables from the spacecraft on one plot, and it can let you zoom in and do various actions.

Certain actions I've learned allows zooming in, being able to obtain certain values, spliting data into individual components, removing plots, and downloading data as txt files (can later be converted into csv). One way I've utilized these commands is by working to plot count rates alongside with the tangent altitude of the MAVEN spacecraft from Scorpius X-1, an extra-solar X-ray source.

## Scorpius X-1

<img src="/images/4_3_26 Graph.png" alt="IDL Tplot" style="display: block; margin: 0 auto; width: 100%; max-width: 1200px; border-radius: 10px; margin-bottom: 20px;">

This graph here shows data during an ideal time when MAVEN was able to detect X-ray photons from Scorpius X-1 (March 12-14, 2016). There is a slight uptick in most of the detectors at the bottom of the graph, characterized by the uptick in the purple graph called "SEP INFOV," showing a correlation that the spacecraft sees it.

My goal was to relate the tangent altitude of the spacecraft from Scorpius X-1 to the count rate from an ideal component of the SEP instruments. Here, it was SEP2R B-F, and I worked to clean out data until I obtained the graph below, which shows only core components that I needed for analysis.

<img src="/images/4_15 Graph Complete.png" alt="IDL Tplot" style="display: block; margin: 0 auto; width: 100%; max-width: 1200px; border-radius: 10px; margin-bottom: 20px;">

After this, I perfomed a command that downloaded the graphed data into txt files, which I formed into a csv file that was loaded and plotted in Jupyter Notebook. The result is the graph below, which plots count rate data from 11 orbits over the 2-day period. As the spacecraft passed the 50 km mark in tangent altitude, count rates significantly increased, proving that the spacecraft was observing Scorpius X-1 at that time.

<img src="/images/Ultimate Tanalt Graph.png" alt="Jupyter Plot" style="display: block; margin: 0 auto; width: 100%; max-width: 1200px; border-radius: 10px; margin-bottom: 20px;">

## GRB 221009A

The brightest ever-observed gamma-ray burst (GRB) occured on October 9, 2022, and is nicknamed the BOAT (Brightest Of All Time). It is at a redshift of z=0.151, and a wide array of spacecraft were able to detect the gamma ray flashes, including the MAVEN SEP instruments.

<img src="/images/Incident_Fluxes_SEP1.png" alt="IDL Tplot" style="display: block; margin: 0 auto; width: 100%; max-width: 1200px; border-radius: 10px; margin-bottom: 20px;">

Four peaks resulted from the GRB. The first of which was too faint to be detected by SEP, but the next three can be seen here. The second and third pulses were observed between 13:24:40 and 13:25:30 UTC. Between 13:29 and 13:30, the fourth, fainter afterglow peak appears. MAVEN observed these pulses 237 seconds after their detection on Earth.

One of the challenges with analyzing this data is obtaining a proper flux of the gamma ray photons. SEP was primarily designed to observe ions, so ground calculations of fluxes are done with this assumption. Because of this, the spectra above are in units of count rate energies. Even though MAVEN had other instruments that were capable of measuring Mars' ionosphere, the spacecraft wasn't close to it when the GRB occured for just a few minutes.

The ultimate goal of this project is to predict the gamma ray flux that SEP detected, and apply it to Mars's atmosphere and ionosphere to observe its effects. There were subtle brief changes in Earth, so it must also be true at Mars.

The solution is to use Geant4 simulation data that models gamma ray photons interacting with the SEP instrument. By using data from Patrick A Dunn's simulations at SSL, I was able to create response matrices that plotted the incident and deposited energies of each photon. The graph below shows the numpy response matrix of each detector from one simulation.

<img src="/images/Seed 03 Response Matrix.png" alt="Jupyter Plot" style="display: block; margin: 0 auto; width: 100%; max-width: 1200px; border-radius: 10px; margin-bottom: 20px;">

Next, I downloaded the spectra data that observed the GRB from IDL, and formatted them to be multiplied by the response matrices from each simulation to obtain a predicted incident flux. As of the writing of this passage, the representation of these incident fluxes are still in progress.

<!-- I am proud to say that I will be continuing this work, headed into the summer, as I plan to analyze data further to study pickup ions and gamma ray bursts with the SEP instruments. -->