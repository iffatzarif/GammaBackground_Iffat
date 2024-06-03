# Optimization of Energy Threshold for the Muon-Veto System
The repository contains all files used to calcuate the optimal the energy threshold to minimize the gamma background counts from the muon-veto system of CUORE while keeping the maximum number of muon counts. A presentation on the project and the background required for the project is also included -- titled "Presentation_YURA+SPS_Final". The muon-veto system counts the number of muons hitting the scintilator panels so that the counts can be eliminated from the CUORE TE-130 detector data so that it can be free from muon background. The muon detector system itself has background in the form of gamma rays, which leads to false positive events in the muon detector such that more of the TE-130 detector data is removed and we have deadtime in the detector. To prevent such an occurence, we try to reduce the gamma background as much as possible. The proposed idea for this is to set an energy threshold for the muon detector and remove all data that is below this energy threshold. This is possible because gamma rays peak at a lower energy than muons as seen in the graph below. From the title of the previous graph, it is evident that the graphs are plotted with simulations rather than detector data. Unlike the former, the latter cannot distinguish between muon and gamma hits -- which is why an energy threshold is required. We try to find a threshold whereby maximum possible number of the gamma counts are below that energy and maximum possible number of muon counts are above. 

<img width="544" alt="image" src="https://github.com/izsneha2004/GammaBackground_Iffat/assets/125691055/8a222b02-b2ba-4cee-9745-30a6b8c09fc8">

The steps for the process include:
1. Simulate gamma and muons data with CUORE’s simulations software with on-site conditions.
2. Use the system response of the detector to smear the simulated data so that it better resembles the on-site detector output. 
3. Draw a cumulative counts curve with varying energy thresholds.
4. Find optimal energy to minimize gamma count, while maximizing muon count. 

For the second step, the system response that Din-Ammar Tolj created in the summer of 2023 is used. The original code and the description can be found here: https://github.com/sgrobnik/SmearingProjectCUORE/tree/main. The system response function smears the simulations data such that it more closely models the real data from the detector. This needs to be done because real detector data is not perfect. The signals that particles produce are modified by their interactions with the detector components and the surroundings. Thus, they produce an output distinct from the one that a simulations software would produce (which would indeed be perfect). It is impossible to make the detector signals perfect and so we modify our simulations signals to match. Different normal distribution models with different variances were tried to find the one that made the data simulated for the lab model the data detected by the panels in the lab most closely. The one that was finally used here is the linear variance model -- though more work can yet be done to improve the model. 

<img width="335" alt="image" src="https://github.com/izsneha2004/GammaBackground_Iffat/assets/125691055/3d22ea9b-8494-47da-834f-b34876ef7f13"> <img width="342" alt="image" src="https://github.com/izsneha2004/GammaBackground_Iffat/assets/125691055/8ed9d29c-a7e4-4034-9e93-88c87b8c1199">

The cumulative counts curve that the third step speaks of is plotting the cumulative gamma counts below the threshold along with the cumulative muon counts above the threshold 
as they are both quantites we are trying to minimize. The graph for LNGS simulations (system response was found using lab data but we are ultimately trying to use on-site data to find the energy threshold that is applicable to the muon panels in their final location) is shown below: 

<img width="572" alt="image" src="https://github.com/izsneha2004/GammaBackground_Iffat/assets/125691055/e1fa8552-2ca6-4342-8a3a-2caecbff440e">

The point in the graph at which both the plotted quantitues maximize is our desired energy threshold. This could be the point at which the two graphs meet but it might be possible to eliminate the gammas altogether if the trend in the graph shown holds for gammas and muons in general since the gammas quickly fall off after the meeting point while muons stay roughly the same. However, it is not known if the trend holds for all gammas and muons as the simulated sample used here is quite small and many of the bins are completely empty. Therefore, we need to run the same code on a bigger dataset. 

Next Steps:
1. Improve system response by adapting to data taken at the Laboratori Nazionali del Gran Sasso (LNGS) in Italy. 
2. Work with simulated data with higher counts to determine a satisfactory energy threshold. 





