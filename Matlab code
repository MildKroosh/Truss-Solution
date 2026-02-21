clc;
clear;
syms FAB FBC FCD FAE FED FBE FCE Ey
c60 = cosd(60);
s60 = sind(60);

%% Joint A
eq1 = FAB*c60 + FAE == 0;
eq2 = FAB*s60 == 0;

%% Joint B
eq3 = -FAB*c60 + FBC + FBE*(2/4) == 0;
eq4 = -FAB*s60 - FBE*(3.464/4) == 0;

%% Joint C
eq5 = -FBC + FCD*c60 - FCE*(2/4) == 0;
eq6 = FCD*s60 - FCE*(3.464/4) == 0;

%% Joint D
eq7 = -FCD*c60 - FED == 0;
eq8 = -FCD*s60 - 8 == 0;

%% Joint E
eq9  = Ey - FBE*(3.464/4) - FCE*(3.464/4) == 0;
eq10 = FAE + FED + FBE*(2/4) - FCE*(2/4) == 0;

sol = solve([eq1 eq2 eq3 eq4 eq5 eq6 eq7 eq8 eq9 eq10], ...
            [FAB FBC FCD FAE FED FBE FCE Ey]);

disp('Member Forces (kN):')
fprintf('FAB = %.2f\n', double(sol.FAB))
fprintf('FBC = %.2f\n', double(sol.FBC))
fprintf('FCD = %.2f\n', double(sol.FCD))
fprintf('FAE = %.2f\n', double(sol.FAE))
fprintf('FED = %.2f\n', double(sol.FED))
fprintf('FBE = %.2f\n', double(sol.FBE))
fprintf('FCE = %.2f\n', double(sol.FCE))

disp('Support Reactions:')
fprintf('Ey = %.2f kN\n', double(sol.Ey))
