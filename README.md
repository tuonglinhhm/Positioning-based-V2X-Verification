# 5GPositioning
This is a demonstration of 5G mmWave positioning

The matlab code (main.m) generates a 2D environment with random scatterers and line-of-sight (LOS) 
between a transmittee (with unknown location and orientation) and a receiver (0,0). 
Both the transmitter and receiver are equipped with uniform linear arrays 
The transmitter sends a sequence of beams, with associated precoders, to the receiver.
At the receiver, the time-of-arrival (TOA), angle-of-arrival (AOA), and angle-of-departure (AOD) 
are estimated using distributed compressed sensing (DCSSOMP.m) in the beamspace domain. 
The LOS parameters are then utilized to recover the receiver's location and orientation. 


![scenario](figs/system.png)

*This figure shows the scenario with a single scattering point.*

```
L=4;                
Rs=5900;             % total BW in MHz
N=2048;             % number of subcarriers 
Nt=32;              % number of TX antennas
Nr=Nt;              % number of RX antennas
Nb=Nt*2;            % number of beams in dictionary; 
Ns=20;              % number of beams sent
c=300;              % speed of light meter / us
Ts=1/Rs;            % sampling period in us
posTx=[5 500]';      % TX (user) position, RX is assumed to be in [0, 0]
velocityTx = 20;     % Velocity of TX
velocityRx = 20;     % Velocity of TX
alpha=0.45;           % user orientation
sigma=0.1;          % noise standard deviation
```
Note that for the code to be able to estimate the distance, the number of subcarriers should be greater than 1. 