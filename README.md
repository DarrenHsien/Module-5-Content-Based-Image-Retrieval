# Module-5-Content-Based-Image-Retrieval


1.視覺詞彙模型概念

  -將圖像表示為無序的圖像塊集合
  
  -一張圖像會擁有好幾個不同區塊 : 例如一張人臉，會有眼睛、鼻子、嘴巴等等
  
  -我們可以透過影像描述相關演算法，萃取出每個區塊圖像對應的特徵向量
  
  -假設同時擁有(人臉(眼睛、鼻子、嘴巴)、腳踏車(輪子、車身、齒輪)、馬克杯(手把、圓弧杯身))，所有的區塊特徵向量都會被無序的蒐集再一個大型的圖塊袋內
  
  -當我們輸入一張人臉，經過分析區塊特徵分析，展示出一個與大型圖塊袋比較的直方圖(輸入影像的分散圖塊與大型圖塊雷同出現次數直方圖)，可以發現鼻子、眼睛等出現次數遠大過其他圖塊雷同的次數，透過這種方式可以辨識出其為人臉
  
2.實際應用 : 
  
  1.圖像區塊特徵提取(透過keypoint萃取其周圍影像描述(SIFT,SURF..))，並使用HDF5儲存.hdf5檔
  
    -hdf5資料庫
      
      -image_ids : 儲存影像標號
    
      -index : 儲存每張圖像特徵向量index起始於結束位置
      
      -features : 圖像萃取出來的特徵向量

  2.產生視覺單詞(影像的視覺單詞其實就是把所有特徵向量拋入，透過聚類分出不同的群，每一群都是一個視覺單詞)
  
    -MiniBatchKMeans : 使用K-Means分群，每一群都可視作一個視覺單詞

    -分成64個集群(64個視覺單詞)

  3.查看視覺單詞在圖像中的樣貌
  
  


