# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:

![WhatsApp Image 2025-11-20 at 11 08 56 AM](https://github.com/user-attachments/assets/c9efad0c-73d1-4000-9580-7eccaaad74c0)
![WhatsApp Image 2025-11-23 at 5 53 15 PM](https://github.com/user-attachments/assets/20d0408d-faeb-4edf-8448-1be7c7cef85c)
<img width="944" height="1280" alt="image" src="https://github.com/user-attachments/assets/18264a16-efab-4de5-80a9-5e00ef2fdf22" />

## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[1]
den = conv([1 0], conv([0.5 1], [0.2 1]));
sys=tf(num,den)
w=logspace(-1,2,1000);
[mag phase]=bode(sys,w);
mag=squeeze(mag);
phase=squeeze(phase);
theta=deg2rad(phase);
polarplot(theta,mag,'LineWidth',1.5)
[gm pm wpc wgc]=margin(sys)
if (wpc>wgc)
    disp('stable')
elseif (wpc==wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```
## Output:

<img width="1210" height="997" alt="image" src="https://github.com/user-attachments/assets/73b21a74-0aa8-485f-a42f-46132df3dc60" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 7.0000<br>
Phase Margin = 55.6412 degree<br>
Gain crossover frequency = 0.8979 rad/s<br>
Phase crossover frequency = 3.1623<br>
The system is  Stable.
