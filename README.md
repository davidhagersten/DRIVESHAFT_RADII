# DRIVESHAFT_RADII
DRIVESHAFT_RADII


%CALC RADII ON THE DRIVESHAFTS

clc
clear all


%LEFT DRIVE SHAFT (RIGHT SIDE)
radii = 31.2;
dist_zero = 362.46;
Y_start = 0;
TABLE_VALUES = zeros(90,3);
END_X = -371.03;



i = 0;
for X = 0:0.10:(8.57)
    i=i+1;
    TABLE_VALUES(i,1) = -(X + dist_zero);
    TABLE_VALUES(i,2) = 2*(radii-sqrt(radii^2-X^2));
    %TABLE_VALUES(i,3) = 2*(radii-sqrt(radii^2-X^2))+0.05;     %Y-VÄRDEN MED MARGINAL FÖR SLIPNING
    
    %DIAMETER COMPENSATED WITH 0.1 mm
%     TABLE_Y(i) = sqrt(radii^2-X^2)-30
end
TABLE_VALUES (i+1,1) = END_X;
TABLE_VALUES (i+1,2) = 2*(radii-sqrt(radii^2-8.57^2));
TABLE_VALUES



%LEFT DRIVE SHAFT (LEFT SIDE)
radii = 30;
dist_zero = 362.46;
Y_start = 0;
LEFT_TABLE_VALUES = zeros(90,3);
END_X = 8.57;



i = 0;
for X = 0:0.10:(8.57)
    i=i+1;
    LEFT_TABLE_VALUES(i,1) = X;
    LEFT_TABLE_VALUES(i,2) = 2*(radii-sqrt(radii^2-X^2));
    %LEFT_TABLE_VALUES(i,3) = 2*(radii-sqrt(radii^2-X^2))+0.05;     %Y-VÄRDEN MED MARGINAL FÖR SLIPNING
    
    %DIAMETER COMPENSATED WITH 0.1 mm
%     TABLE_Y(i) = sqrt(radii^2-X^2)-30
end
LEFT_TABLE_VALUES (i+1,1) = END_X;
LEFT_TABLE_VALUES (i+1,2) = 2*(radii-sqrt(radii^2-8.57^2));
LEFT_TABLE_VALUES
