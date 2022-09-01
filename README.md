# AIdea_problem_practice
## marathoon
### step1: data processing
<br>
1. 先觀察train.csv檔案的資料,將同樣mac_hash這一欄資料的sniffer_loc合併起來
</br>
<img width="245" alt="image" src="https://user-images.githubusercontent.com/112559944/187919803-e6ff4344-6582-4baf-9f9c-3aefaf4e319d.png">
<br>
寫進csv時分為了sniffer_loc 0-13的欄位，缺值補0
</br>
<img width="207" alt="image" src="https://user-images.githubusercontent.com/112559944/187920058-1c591d3e-b841-4582-ac36-77b0bf9d9fb6.png">
<img width="340" alt="image" src="https://user-images.githubusercontent.com/112559944/187920124-d20b8607-10c6-47e5-a2be-d36c28f39e63.png">
<br>
2. 觀察training-label.csv檔案的資料。要將label轉換為0-1的範圍便於之後模型的建立及訓練
<img width="153" alt="image" src="https://user-images.githubusercontent.com/112559944/187920309-4a253984-40c2-4740-ab90-5387aa8ede08.png">
建立0-4的label list,根據label的值去分別存list，與值相等時就append 1，其他為0,將label轉化為0-1的形式
<img width="255" alt="image" src="https://user-images.githubusercontent.com/112559944/187920459-480c50e3-3071-4840-a2bb-b1be0c153bdc.png">
轉變為
<img width="336" alt="image" src="https://user-images.githubusercontent.com/112559944/187920541-40677cc1-998f-4304-9752-0d2f68d55ef2.png">
儲存為新的newlabel.csv檔案
</br>
<br>
3. 合併檔案：將新的label的檔案與新的train的檔案合併在一起。這裡將created_time這一欄資料刪除，沒有列入考慮。
<img width="415" alt="image" src="https://user-images.githubusercontent.com/112559944/187921028-85909b46-4737-4ad3-8fd9-961c3b57609b.png">
合併後資料共19欄
</br>
<br>
4. 設定解釋變數及目標變數：
<img width="415" alt="image" src="https://user-images.githubusercontent.com/112559944/187921335-96398043-8510-495a-a198-833791d5fadb.png">
解釋變數為sniffer_loc 0-13 共14項資料，而目標變數（預測值）為label_0到label_4五項資料，
在用info()觀察最後資料的型態是否都為int及float等數值型態。
</br>
### step2: build model and model test
<br>
1.	使用的為DNN模型
<img width="289" alt="image" src="https://user-images.githubusercontent.com/112559944/187921929-b4ff23e3-1eb2-4768-9c7d-4349eef0367a.png">
input dim=14,解釋變數為14項
units=5，目標變數為5項
</br>
<br>
2. 數據標準化及訓練模型
<img width="308" alt="image" src="https://user-images.githubusercontent.com/112559944/187922408-c5e73ff2-c19e-40af-b312-82343936083b.png">
其中epoch數我設為100
最後的訓練準確度的結果為93%左右
<img width="248" alt="image" src="https://user-images.githubusercontent.com/112559944/187922712-32e4c97d-cf11-4112-a6a5-2a0b2b3c1e28.png">
</br>
<br>
3. 模型儲存及對test.csv檔案資料進行預測
對test.csv一樣做前處理，用儲存後的模型做測試
最後上傳AIdea的結果：
<img width="415" alt="image" src="https://user-images.githubusercontent.com/112559944/187923305-f808e09d-6ae0-4c5b-bdd2-d6bbbb87a5b0.png">
</br>

## AOI
### step1: data processing
<br>
1.使用colab環境，Mount the Drive及讀取資料
<img width="208" alt="image" src="https://user-images.githubusercontent.com/112559944/187923848-3e18b1d0-95d6-4ff6-9820-22eee016a135.png">
2.新增資料夾及分類圖片,label有六種，因此產生0-5 label的資料夾
<img width="319" alt="image" src="https://user-images.githubusercontent.com/112559944/187924176-dda3f50b-16ee-4411-a684-81cd2d8fc533.png">
3. 處理圖片
圖片標準化及分割圖片資料，分割80%為測試資料，20%為驗證資料。
</br>

### step2: build model,train and test
<br>
1. use Keras VGG16 pretrained model:
<img width="354" alt="image" src="https://user-images.githubusercontent.com/112559944/187924572-c8737c64-1600-44e1-b80d-db122c4b576f.png">
<img width="297" alt="image" src="https://user-images.githubusercontent.com/112559944/187924612-0cd04f73-9985-4d29-a1dd-61b9e32943ad.png">
2. use test images file to test model and result:
<img width="415" alt="image" src="https://user-images.githubusercontent.com/112559944/187924764-08ff81e0-c665-4c0b-ba1b-9b23dc03f4a6.png">
</br>



















