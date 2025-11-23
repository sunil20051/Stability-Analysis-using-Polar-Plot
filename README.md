# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
![WhatsApp Image 2025-11-18 at 14 37 29_de6ff983](https://github.com/user-attachments/assets/3d8e0853-4647-46a5-8fa5-69f02cbd2197)
![WhatsApp Image 2025-11-18 at 14 37 29_89f9a247](https://github.com/user-attachments/assets/b29d6eab-9eab-429a-bfd2-ef889992b9c7)



## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
num=[1] <br>
den=[conv(1,0),conv(1,0.5),conv(1,0.2)] <br>
sys=tf(num,den) <br>
w=logspace(-1,2,1000)<br>
[mag phase]=bode(sys,w) <br>
mag=squeeze(mag) <br>
phase=squeeze(phase) <br>
theta=deg2rad(phase) <br>
polarplot(theta,mag,'LineWidth',1.5) <br>
[gm pm wpc wgc]=margin(sys) <br>
if (wpc>wgc) <br>
    disp('stable') <br>
elseif (wpc==wgc) <br>
    disp('marginally stable') <br>
else <br>
    disp('unstable') <br>
end

## Output:
<img width="1917" height="1033" alt="image" src="https://github.com/user-attachments/assets/c40f4be1-5c11-4f5b-9f25-c49315b3a15e" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 0.70 <br>
Phase Margin = -13 <br>
Gain crossover frequency = 3.75<br>
Phase crossover frequency = 3.16<br>
The system is unstable
