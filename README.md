Matlab code for V2X Verification

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
