___
##### **Approach next** | Some questions?
 | using other functions than relu?  
 | Training & predicting men & women seperately?  
 | How does unscaled data looks?  
 | Not supposed to use 2024 data.  
 | Using softmax & cross entropy as its more meaningfull  

___
##### **Approach 18** | **increase memory further** of model  
'Training for year: 2022 | epochs: 200 | years_cap: None | aprch: 18 ...'  
'0.58858 Loss (binary_crossentropy) 0.65344 val_loss | 0.20607 mse (Brier score) 0.22818 val_mse | Epoch 10 / 200'  
'0.55379 Loss (binary_crossentropy) 0.96637 val_loss | 0.19416 mse (Brier score) 0.27326 val_mse | Epoch 20 / 200'  
'0.53477 Loss (binary_crossentropy) 1.83196 val_loss | 0.18755 mse (Brier score) 0.30468 val_mse | Epoch 30 / 200'  
'0.48131 Loss (binary_crossentropy) 18.48592 val_loss | 0.16889 mse (Brier score) 0.28990 val_mse | Epoch 180 / 200  
'0.48008 Loss (binary_crossentropy) 17.63218 val_loss | 0.16898 mse (Brier score) 0.29508 val_mse | Epoch 190 / 200  
'0.48789 Loss (binary_crossentropy) 23.29853 val_loss | 0.16906 mse (Brier score) 0.34621 val_mse | Epoch 200 / 200  
'Time taken to fit the model: 6:34:22'  
Model: "sequential_21"  
| Layer (type)  | Output Shape   |Param # |
|------|------|------|
|dense_71 (Dense) | (None, 760) | 571,520 |
|dense_72 (Dense) | (None, 760) | 578,360 |
|dense_73 (Dense) | (None, 760) | 578,360 |
|dense_74 (Dense) | (None, 1) | 101 |

 Total params: 5,187,005 (19.79 MB)  
 Trainable params: 1,729,001 (6.60 MB)  
 Non-trainable params: 0 (0.00 B)  
 Optimizer params: 3,458,004 (13.19 MB)
 
why its printing in **scientific notation?**

'0.293086 brier_score for year 2022'
||Pred_Prob| 	True_Outcome|
|-|-|-|
|0 	4.95e-01| 	1|
|1| 	2.46e-12| 	0|
|2 	|4.95e-01 	|1|
|3 	|4.95e-01 	|0|
|4 	|4.95e-01 	|1|

'0.394866 brier_score for year 2023'
||	Pred_Prob| 	True_Outcome|
|-|-|-|
|0| 	6.41e-01 	|0|
|1| 	1.00e+00 	|0|
|2| 	1.56e-06 	|1|
|3| 	1.18e-16 	|1|
|4| 	1.00e+00| 	1|

___
##### **Approach 17** | **increase memory of model**  
 >| **model should have memory**: for prediction it need to remember the teams & their weights  
 | 364 men + 361 woment ==> total = 725 teams  
 | Say 3 hidden layers with 100 nodes each ==> (100*100)+(100*100) = 20,000 weigths
 
'Training for year: 2022 | epochs: 200 | years_cap: None | aprch: 16  ...'  
'0.60741 Loss (binary_crossentropy) 0.70025 val_loss | 0.21298 mse (Brier score) 0.23602 val_mse | Epoch 10 / 200'  
'0.51047 Loss (binary_crossentropy) 2.77062 val_loss | 0.17848 mse (Brier score) 0.35104 val_mse | Epoch 200 / 200   
Model: "sequential_14"
| Layer (type)  | Output Shape   |Param # |
|------|------|------|
|dense_43 (Dense) | (None, 100) | 75,200 |
|dense_44 (Dense) | (None, 100) | 10,100 |
|dense_45 (Dense) | (None, 100) | 10,100 |
|dense_46 (Dense) | (None, 1) | 101 |

Total params: 286,505 (1.09 MB)  
 Trainable params: 95,501 (373.05 KB)  
 Non-trainable params: 0 (0.00 B)  
 Optimizer params: 191,004 (746.11 KB)  

'0.360923 brier_score for year 2022'
||Pred_Prob| 	True_Outcome|
|-|-|-|
|3| 	0.06| 	0|
|4 	|0.90| 	1|

'0.400066 brier_score for year 2023'
||Pred_Prob| 	True_Outcome|
|-|-|-|
|0| 	7.53e-01| 	0|
|1| 	9.69e-01 |	0|
|2 |	5.44e-01 	|1|
|3 	|2.87e-02| 	1|
|4 	|1.63e-01 |	1|

___
##### **Approach 16** | train full data  
 'Training for year: 2022 | epochs: 200 | years_cap: None | nodes_hidn_lyr: 50 | aprch: 16 ...'  
 Model: "sequential_12"  
| Layer (type)  | Output Shape   |Param # |
|------|------|------|
|dense_36 (Dense) | (None, 50) | 37,600 |
|dense_37 (Dense) | (None, 50) | 2,550 |
|dense_38 (Dense) | (None, 1) | 51 |

 Total params: 120,605 (471.12 KB)  
 Trainable params: 40,201 (157.04 KB)  
 Non-trainable params: 0 (0.00 B)  
 Optimizer params: 80,404 (314.08 KB)  

'0.61877 Loss (binary_crossentropy) 0.64040 val_loss | 0.21722 mse (Brier score) 0.21811 val_mse | Epoch 10 / 200'  
'0.60193 Loss (binary_crossentropy) 0.61871 val_loss | 0.21066 mse (Brier score) 0.20955 val_mse | Epoch 20 / 200'  
'0.55719 Loss (binary_crossentropy) 0.86180 val_loss | 0.19384 mse (Brier score) 0.25455 val_mse | Epoch 200 / 200'  
'0.254551 brier_score for year 2022'  
'0.343427 brier_score for year 2023'  
>optimizing cross entropy (this) vs mse  (aproch 14)  
training brier score is similar (0.1938 vs 0.1988) | val loss improved a bit (0.254 vs 0.275)  
**worse score** due to **capped training data**

___
##### **Approach 15** | output node = Sigmoid, **cross entropy for loss function**  
| training data **restricted to 2 years**  
| 2 hidden layers with 100 nodes each ==> 50 x 50 = 2500 weigths  
'Training for year: 2022 | epochs: 200 | years_cap: 2 | nodes_hidn_lyr: 50 | aprch: 15 ...'  
 2022  
'0.43268 Loss (binary_crossentropy) 2.79712 val_loss | 0.15513 mse (Brier score) 0.42693 val_mse | Epoch 200 / 200'  
**worse score** than optimizing with mse (0.4269 vs 0.245)

___
##### **Approach 14** | Correct **Briar score** (outcome than probability)  
| What metric compares with score? mse is far off!! **Briar score matches it**  
'Training for year 2022 ...'  
'0.198936 Loss | 0.267952 val_loss | Brier score with mse | Epoch 195 / 200'  
'0.198883 Loss | 0.291184 val_loss | Brier score with mse | Epoch 196 / 200'  
'0.198833 Loss | 0.279018 val_loss | Brier score with mse | Epoch 197 / 200'  
'0.198817 Loss | 0.282074 val_loss | Brier score with mse | Epoch 198 / 200'  
'0.198847 Loss | 0.280075 val_loss | Brier score with mse | Epoch 199 / 200'  
'0.198808 Loss | 0.275084 val_loss | Brier score with mse | Epoch 200 / 200'  
'0.198808 | Best loss '  
**training loss went down** (0.19) but not the **evaluation loss** (0.24)  
'0.245065 brier_score for year 2022'  
'0.267237 brier_score for year 2023'  

___
##### **Approach 13** |  
 | Sample Submission (prediction=0.5) for all matches | Kaggle score: **0.2500**  
 | our prediction 0.24xx is better only **1  
 | mse on sample submission 0.5 is '**0.0048** | Metric mean_squared_error on Probability'  
 | Kaggle score is different than mse, though on its website is clamis to be mse  
 | or some calculation in this notebooks is wrong  

___
##### **Approach 12** | check again kaggle score on unscaled | Kaggle score: **0.24811**  
'4m callback | best Loss: 0.025430 | corresponding miss_pred: 0.222222'  
"Evaluating best_loss model's predictions for year 2023 ..."  
'**0.0057** | Metric mean_squared_error on Probability' | **metric not matching with score**  
'0.0990 | Metric mean_squared_error on Strength'  
"0.4627 | 62/134 | Mis predicted Match's outcome | Probabilities"  

11 vs 12 | **NAN is present in 12 but not in 11 !!**  
**Why is tru prob is NAN as well?**  
Pred_Prob 	True_Prob 	Pred_Prob 	True_Prob  
 	1.17 	0.43 	NaN 	NaN  
 	1.15 	0.49 	NaN 	NaN  
 	1.16 	0.45 	NaN 	NaN  
 	1.17 	0.34 	NaN 	NaN  
 	1.15 	0.34 	NaN 	NaN  

**NaN is coming due to concat**  | **Not a prediction issue**
Final concat  
Pred_Prob  True_Prob  Pred_Prob  True_Prob  
0         0.51       0.50       0.57       0.50  
1         0.51       0.49       0.60       0.49  
**10**        0.51       0.41        NaN        NaN  

**index 10** is **present in only 1 mis pred**  
     Pred_Prob  True_Prob  
0         0.51       0.50  
1         0.51       0.49  
**10**        0.51       0.41  

 Pred_Prob  True_Prob  
0         0.57       0.50  
1         0.60       0.49  
8         0.39       0.50  
**11**        0.46       0.51  

**Intersting** thing is with **appr 11 | unscaled** most of the **predictions are same = 0.51 | 1.04 **  
**Scaling is the way to go**  
Looking in apr11 submition most of the predictions are **2023_1158_1396│0.5098786**
>**apr 11 | Scaled**  
'Predicted vs actual | Strength | Winning prob'  
     Pred_Strength  True_Strength  Pred_Prob  True_Prob  
0             1.04           0.98       **0.51**       0.50  
1             1.04           0.95       **0.51**       0.49  
2             1.04           1.34       **0.51**       0.57  
3             1.04           1.38       0.51       0.58  
4             1.04           1.28       **0.51**       0.56  
5             1.04           1.16       0.51       0.54  
6             1.04           1.11       **0.51**       0.53  
7             1.04           1.45       0.51       0.59  
8             1.04           1.01       **0.51**       0.50  
9             1.04           1.21       0.51       0.55  
10            1.04           0.71       0.51       0.41  

>**apr 12 | UnScaled**  
'Predicted vs actual | Strength | Winning prob'  
     Pred_Strength  True_Strength  Pred_Prob  True_Prob  
0             1.34           0.98       **0.57**       0.50  
1             1.48           0.95       **0.60**       0.49  
2             1.04           1.34       **0.51**       0.57  
3             1.05           1.38       0.51       0.58  
4             2.04           1.28       **0.67**       0.56  
5             1.30           1.16       0.57       0.54  
6             1.41           1.11       **0.59**       0.53  
7             2.10           1.45       0.68       0.59  
8             0.64           1.01       **0.39**       0.50  
9             1.55           1.21       0.61       0.55  
10            0.84           0.71       0.46       0.41  

___
##### **Approach 11** | Unscaled | Kaggle score: **0.24988**  
'4m callback | best Loss: 0.072745 | corresponding miss_pred: 0.555556'  
"Evaluating best_loss model's predictions for year 2023 ..."  
'**0.2848** | Metric mean_squared_error on Probability' | **metric is close to kaggle score**  
'804.3482 | Metric mean_squared_error on Strength'  
"0.4851 | 65/134 | Mis predicted Match's outcome | Probabilities"  
"0.5373 | 72/134 | Mis predicted Match's outcome | Strength"  

___
##### **Approach 10** |  How does **training with probablity** compare with strength?  
 | Train on probability  
 | How does it compare with Strength?  
 | Save best miss pred when loss < 0.00146  
 | **Looks probability & strength are similar**: Probability is slightly worst **kaggle score 0.28 vs 0.24**  
 | **Its varying run to run** *Lets stick to Strength*  
'4m callback | best Loss: 0.001445 | corresponding miss_pred: 0.166667'  
'4m callback | best miss_pred: 0.055556 | corresponding loss: 0.001450'  
"Evaluating best_loss model's predictions for year 2023 ... | Kaggle score: **0.28311**"  
'0.0035 | Metric mean_squared_error on Probability'  
'0.0737 | Metric mean_squared_error on Strength'  
"0.3731 | 50/134 | Mis predicted Match's outcome | Probabilities"  
"0.3731 | 50/134 | Mis predicted Match's outcome | Strength"  
"Evaluating best_mis_pred model's predictions for year 2023 ...| Kaggle score: **0.2826**"  
'0.0036 | Metric mean_squared_error on Probability'  
'0.0736 | Metric mean_squared_error on Strength'  
"0.3806 | 51/134 | Mis predicted Match's outcome | Probabilities"  
"0.3806 | 51/134 | Mis predicted Match's outcome | Strength"  

___
##### **Approach 9** |  How does **training with probablity** compare with strength?  
 | Train on probability  
 | How does it compare with Strength?  

___
##### **Approach 8** |  **optimize mis calculations than mse** it failed to differntiate  
 | Save the best_fit & best_mis_pred models (constrained such that loss <0.26 as well)  
 | **May be predictions did not improve**  
 | all the ANN predictions scores are **0.24ish**  
 | May be **need a drastically new approach** to better scores further  
 "Evaluating best_loss model's predictions for year 2023 ... | Kaggle score: **0.24310**"  
'0.0040 | Metric mean_squared_error on Probability'  
'0.0792 | Metric mean_squared_error on Strength'  
"0.4104 | 55/134 | Mis predicted Match's outcome | Probabilities"  
"0.4104 | 55/134 | Mis predicted Match's outcome | Strength"  

"Evaluating best_mis_pred model's predictions for year 2023 ... | Kaggle score: **0.24270**"  
'0.0039 | Metric mean_squared_error on Probability'  
'0.0790 | Metric mean_squared_error on Strength'  
"0.4030 | 54/134 | Mis predicted Match's outcome | Probabilities"  
"0.4030 | 54/134 | Mis predicted Match's outcome | Strength"  
 
 ___
 ##### **Approach 7** | Kaggle score: ****  
 | Save the best_fit & best_mis_pred models  
 "Evaluating best_loss model's predictions for year 2023 ..."  
'0.0046 | Metric mean_squared_error on Probability'  
'0.0909 | Metric mean_squared_error on Strength'  
"0.4328 | 58/134 | Mis predicted Match's outcome | Probabilities"  
"0.4328 | 58/134 | Mis predicted Match's outcome | Strength"  

"Evaluating best_mis_pred model's predictions for year 2023 ..."  
'0.0042 | Metric mean_squared_error on Probability'  
'0.0824 | Metric mean_squared_error on Strength'  
"0.4030 | 54/134 | Mis predicted Match's outcome | Probabilities"  
"0.4030 | 54/134 | Mis predicted Match's outcome | Strength"  

 ___
 ##### **Approach 6** | Kaggle score: ****  
 | Save the best model  
 'Loss: 0.026098 | mse: 0.026098 | prcnt_miss_preds_strnt: **0.055556** | Epoch 180 / 200'  
'Loss: 0.026028 | mse: 0.026028 | prcnt_miss_preds_strnt: 0.166667 | Epoch 190 / 200'  
'Loss: 0.025889 | mse: 0.025889 | prcnt_miss_preds_strnt: 0.333333 | Epoch 200 / 200'  
'Loss: 0.025889 | Best loss | save_best_model.best'  
'4m callback | best Loss: 0.025889 | miss_pred_corsp_best_loss: 0.333333'  
How about **saving best prcnt_miss_preds_strnt ** | even though it can't be used as loss function

 ___
 ##### **Approach 5** | Kaggle score: **0.24850**  
 | Refit with updated variable names  
 | Correcting the Mis predictions query  
 | Most of the predictions are around 0.5 only !! like 0.52 | 0.48 ...  
 
 ___
 ##### **Approach 4** | 11% -- good for submission | score: 0.24748, leaderboard: 940 / 1033 = 91%  
 | Strength ordered by default = its of small teamID  
 | scaled, 1hot encoded  
 | combined M & W  
 | How is score: 0.24748 is coming ?  
 50 = neuron's count  
 02 = hidden layer's count  

 ___
 ##### **Approach 3** | To submit need to predict for Women as well  
 | Strength by default is ordered = its of small teamID  
 | scaled, encoded  
 | only men  
 50 = neuron's count  
 02 = hidden layer's count

 ___
 ##### **Approach 2** | 25%  
 | Strength by default is ordered = its of small teamID  
 | unscaled & not encoded  
 50 = neuron's count  
 02 = hidden layer's count

 ___
 ##### **Approach 1** | 50% -- Failed: Could predict with only prob 0.5%  
 | Using inverted strength for the order.  
 16 = neuron's count  
 02 = hidden layer's count  """