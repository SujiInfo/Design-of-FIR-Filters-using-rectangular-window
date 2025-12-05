# 4 A Design-of-FIR-Filters-using-rectangular-window
#          DESIGN OF LOW PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM:
```c
// DESIGN OF LOW PASS FIR FILTER USING RECTANGULAR WINDOW

clc;
clear;
close;

// Filter specifications
N = 25;          // Filter length (odd number)
fc = 0.10;       // Normalized cutoff frequency (0 < fc < 0.5)
M = N - 1;
n = 0:M;

// Ideal impulse response (sinc function)
hd = 2 * fc * sinc(2 * fc * (n - M/2));

// Rectangular window
w = ones(1, N);

// FIR filter coefficients
h = hd .* w;

// Frequency response
[H, f] = frmag(h, 1024);   // magnitude response

// ---- Plot impulse response ----
figure(1);
plot2d3(n, h);
title('Impulse Response of FIR Low Pass Filter (Rectangular Window)');
xlabel('n');
ylabel('h[n]');
xgrid();

// ---- Plot magnitude response ----
figure(2);
plot(f, abs(H));
title('Magnitude Response');
xlabel('Normalized Frequency');
ylabel('|H(f)|');
xgrid();

// ---- Display filter coefficients ----
disp("Filter Coefficients (h[n]):");
disp(h');

disp("Filter length (N): " + string(N));
disp("Cutoff frequency (fc): " + string(fc));
disp("Window used: Rectangular");
```

# OUTPUT:

<img width="206" height="405" alt="4c" src="https://github.com/user-attachments/assets/0b9bb4e1-bec3-4a58-850c-34b9ccc0abb5" />


<img width="824" height="398" alt="41" src="https://github.com/user-attachments/assets/46ef7700-10de-4fd4-a0e3-8ef3eefe2558" />


<img width="808" height="398" alt="42" src="https://github.com/user-attachments/assets/f7a56a04-5535-4777-a127-7fe7a6b70b1e" />


# RESULT:

Thus, the design of low pass FIR digital filter using SCILAB was generated successfully.
