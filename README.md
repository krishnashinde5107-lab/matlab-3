% Input and target data
input = [10 20 30 40 50 60 70 80];
target = [20 30 40 50 60 70 80 90];

% Create neural network
net = fitnet(10);

% Train network
net = train(net,input,target);

% Predict output
output = net(input);

% Plot results
plot(target,'r')
hold on
plot(output,'b')
legend('Actual','Predicted')
title('Demand Forecasting using ANN')
