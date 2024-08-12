clc
clear
close
fs=44100;
a=audiorecorder(fs,16,1,1)
b=70;
disp("started recording")
recordblocking(a,b);
disp("stoped recording")
play(a);
y=getaudiodata(a)
figure(1)
subplot(211)
x=fft(y);
......................................................................
x_mag=abs(x)
subplot(212)
plot(x_mag/(fs/2))
title('spectrum of audio')