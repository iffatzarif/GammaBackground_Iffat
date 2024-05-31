# Optimization of Energy Threshold for the Muon-Veto System
The repository contains all files used to calcuate the optimal the energy threshold to minimize the gamma background counts from the muon-veto system of CUORE while keeping the maximum number of muon counts. The muon-veto system counts the number of muons hitting the scintilator panels so that the counts can be eliminated from the CUORE TE-130 detector data so that it can be free from muon background. The muon detector system itself has background in the form of gamma rays, which leads to false positive events in the muon detector such that more of the TE-130 detector data is removed and we have deadtime in the detector. To prevent such an occurence, we try to reduce the gamma background as much as possible. The proposed idea for this is to set an energy threshold for the muon detector and remove all data that is below this energy threshold. This is possible because gamma rays peak at a lower energy than muons as seen in the graph below. From the title of the previous graph, it is evident that the graphs are plotted with simulations rather than detector data. Unlike the former, the latter cannot distinguish between muon and gamma hits -- which is why an energy threshold is required. We try to find a threshold whereby maximum possible number of the gamma counts are below that energy and maximum possible number of muon counts are above. 

<img width="544" alt="image" src="https://github.com/izsneha2004/GammaBackground_Iffat/assets/125691055/8a222b02-b2ba-4cee-9745-30a6b8c09fc8">

The steps for the process include:
1. Simulate gamma and muons data with CUORE’s simulations software with on-site conditions.
2. Use the system response of the detector to smear the simulated data so that it better resembles the on-site detector output. 
3. Draw a cumulative counts curve with varying energy thresholds.
4. Find optimal energy to minimize gamma count, while maximizing muon count. 

For the second step, the system response that Din-Ammar Tolj created in the summer of 2023 is used. The process is 



