Plotting in MATLAB
==============

Drawing an example plot should follow codes below:

```
load('Ux');         % 10Hz Ux as what you used in this tutorial 
load('Timestamp');  % Time points corresponding to Ux
load('Ux_hh');      % Half - hour Ux 
load('Timestamp_plot);% Time points corresponding to Ux_hh
```

You can have a look of these data time points using:

```
datestr(Timestamp);      % This step gonna take you several seconds due to too many time points
datestr(Timestamp_plot); 
```

The codes below would draw a plot showing both 10Hz and Half - hour Ux in the same plot:

```
figure % Create a blank figure
h1=plot(Timestamp,Ux,'k','linewidth',2); % Draw a black line for 10Hz Ux
hold on
h2=plot(Timestamp_plot,Ux_hh,'r','linewidth',2); % Draw a red line for Half - hour Ux
datetick('x','HH:MM:SS'); % Change the x ticks to Hour:Minute:Second version
legend([h1 h2],{'10Hz Ux','Half - hour Ux'}); % Add legends for two lines
xlabel('Time'); % Add label for x axis
ylabel('Ux');% Add label for y axis
set(gca,'fontsize',16);% Make larger fontsize
ylim([-10 10]);% Change the range of y axis to make 0 central
print -dpng -r600 Example_Figure.png % Print the figure
```
![Image text](https://github.com/ZijieZhaoMMHW/ATOC30008_2020_Plot/blob/master/Example_Figure.png)



