
experiment no 3




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




experiment no 4




clc;
clear;

N = 100;          % Number of steps
D = 1;            % Number of dimensions
animate = true;   % true/false for animation

% Initialize position matrix
P = zeros(N,D);

% Generate random steps (-1 or +1)
steps = randi([0 1],N,D)*2 - 1;

% Compute positions
for k = 1:D
    for i = 2:N
        P(i,k) = P(i-1,k) + steps(i,k);
    end
end

% Plotting
figure;
hold on;

for k = 1:D

    if animate
        pause(0.05);
    end

    plot(1:N, P(:,k), 'LineWidth',2);
    hold on;

    % Label each dimension
    text(N, P(N,k), sprintf('Dim %d',k));

end

xlabel('Step #');
ylabel('Position');

if D == 1
    title('Random Walk in 1 Dimension');

elseif D == 2
    title('Random Walk in 2 Dimensions');

else
    title(['Random Walk in ', num2str(D), ' Dimensions']);

end

grid on;





experiment no 5
