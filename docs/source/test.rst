Evaluation Metrics
=============
* F1 Score  
* Running time (Please limit the maximum consumption of GPU memory to 1500MB and RAM to 28GB)


Evaluation Platform
=============
The submitted docker containers will be evaluated on a Ubuntu 20.04 desktop. Detailed information is listed as follows:  

* CPU: Intel® Xeon(R) W-2133 CPU @ 3.60GHz × 12   
* GPU: NVIDIA QUADRO P400 **(Available memory 1500 MB)**    
* RAM: **28G**    
* Driver Version: 510.60.02       
* CUDA Version: 11.6    
* Docker version 20.10.13 


Ranking Scheme
=============
Both F1 score and running time are used in the ranking scheme. However, the two metrics cannot be directly fused because they have different dimensions. Thus, we use a “rank-then-aggregate" scheme for ranking, including the following three steps:	  

* Step 1. Computing the two metrics for each testing case and each team;  
* Step 2. Ranking teams for each of the N testing cases such that each team obtains Nx2 rankings; 
* Step 3. Computing ranking scores for all teams by averaging all these rankings and then normalizing them by the number of teams.
