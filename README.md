# Studying the approach of CLIP4clip[1] for text to video retrieval on the AVSD[2] dataset
Mohammad Amin Nazerzadeh

|                        |    R@1   |    R@5   |   R@10   | MedRank |  MeanRank |
|:----------------------:|:--------:|:--------:|:--------:|:-------:|:---------:|
|     parameter-free     |   17.6   | **40.8** | **51.7** |  **10** |   46.83   |
| sequential transformer | **17.8** |   39.6   |   51.6   |  **10** | **44.13** |
|     sequential lstm    |   14.9   |   35.0   |   48.3   |    12   |   49.46   |
| tight transformer      | 13.1     | 32.1     | 45.7     | 13      | 50.07     |

The previous table shows the final evaluation of the models on the test set. The best values for each metric are shown in Bold. The parameter-free approach, as expected from the results of CLIP4clip [1], performs best on three metrics out of five. After that, the sequential transformer approach performs best on the other two metrics, while the total performance  of these two approaches does not differ significantly. The tight transformer approach performs the worst on the metrics. It shows that it is hard for this approach to learn the cross-modality interaction without larger amounts of data.

 The results are in agreement with the results reported on CLIP4clip and it further confirms their conclusion that simple average pooling on top of CLIP can be best suited on the small-scale text-video retrieval datasets and it is better not to introduce new parameters and adpot a mean pooling mechanism on video frames in these cases.

 [1] Luo, H., Ji, L., Zhong, M., Chen, Y., Lei, W., Duan, N., & Li, T. (2021). CLIP4Clip: An Empirical Study of CLIP for End to End Video Clip Retrieval. ArXiv. /abs/2104.08860
 
 [2] Alamri, H., Cartillier, V., Das, A., Wang, J., Cherian, A., Essa, I., Batra, D., Marks, T. K., Hori, C., Anderson, P., Lee, S., & Parikh, D. (2019). Audio-Visual Scene-Aware Dialog. ArXiv. /abs/1901.09107
