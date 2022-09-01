# AIdea_problem_practice
## marathoon
### step1: data processing
<br>
先觀察train.csv檔案的資料,將同樣mac_hash這一欄資料的sniffer_loc合併起來
</br>
<img width="245" alt="image" src="https://user-images.githubusercontent.com/112559944/187919803-e6ff4344-6582-4baf-9f9c-3aefaf4e319d.png">
<br>
寫進csv時分為了sniffer_loc 0-13的欄位，缺值補0
</br>
<img width="207" alt="image" src="https://user-images.githubusercontent.com/112559944/187920058-1c591d3e-b841-4582-ac36-77b0bf9d9fb6.png">
<img width="340" alt="image" src="https://user-images.githubusercontent.com/112559944/187920124-d20b8607-10c6-47e5-a2be-d36c28f39e63.png">
<br>
觀察training-label.csv檔案的資料。要將label轉換為0-1的範圍便於之後模型的建立及訓練
<img width="153" alt="image" src="https://user-images.githubusercontent.com/112559944/187920309-4a253984-40c2-4740-ab90-5387aa8ede08.png">
建立0-4的label list,根據label的值去分別存list，與值相等時就append 1，其他為0,將label轉化為0-1的形式
<img width="255" alt="image" src="https://user-images.githubusercontent.com/112559944/187920459-480c50e3-3071-4840-a2bb-b1be0c153bdc.png">
轉變為
<img width="336" alt="image" src="https://user-images.githubusercontent.com/112559944/187920541-40677cc1-998f-4304-9752-0d2f68d55ef2.png">
儲存為新的newlabel.csv檔案
</br>









