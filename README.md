# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
<img width="819" height="1280" alt="image" src="https://github.com/user-attachments/assets/5bb0b13c-7111-4394-90f2-1c7a7dffeb34" />
<img width="813" height="1280" alt="image" src="https://github.com/user-attachments/assets/bdad79cb-721f-4bd2-8d29-6db53ac1ddc0" />
<img width="1280" height="859" alt="image" src="https://github.com/user-attachments/assets/fd1cf6e1-cd3f-4c26-920b-da8469a03610" />



## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[10]
den=[0.1 0.7 1 0]
sys=tf(num,den)
[mag,phase,W]=bode(sys)
mag=squeeze(mag)
phase=squeeze(phase)
phase1=deg2rad(phase)
polarplot(phase1,mag,'linewidth',1.5)
grid on
[Gm Pm Wpc Wgc]=margin(sys)
if(Wpc>Wgc)
    disp('stable')
elseif(Wpc == Wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```

## Output:
<img width="702" height="629" alt="image" src="https://github.com/user-attachments/assets/cc1eba6e-26ad-4f25-8a84-e64df4ca3013" />


## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 0.7 <br>
Phase Margin = -8.88 <br>
Gain crossover frequency = 3.75 <br>
Phase crossover frequency =  3.16 <br>
The system is  unstable
