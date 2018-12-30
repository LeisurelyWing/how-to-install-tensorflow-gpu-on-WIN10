# how-to-install-tensorflow-gpu-on-WIN10
如何在WN10安裝tensorflow-gpu


1. 確認顯示卡型號及驅動   
1-1  到tensorflow官網查看硬體需求   
       https://www.tensorflow.org/install/gpu   
       2018年12月，網頁寫的需求為CUDA® Compute Capability 3.5 or higher.   
1-2  到NVIDIA官網檢查自己的顯示卡是否支援Compute Capability 3.5 以上   
       https://developer.nvidia.com/cuda-gpus   
1-3  主流家用顯示卡通常是GeForce系列，點下去後會展開產品列表   
       如果自己的顯示卡不支援就不用繼續看本安裝說明瞭，先改用tensorflow CPU版本吧   
1-4  到tensorflow官網查看顯示卡驅動需求(寫在Software requirements區域)   
       https://www.tensorflow.org/install/gpu   
       2018年12月，網頁寫的需求為 384.x or higher   
1-5 如果自己的顯示卡驅動程式沒達到384.x，先更新驅動   
   
2. 下載並安裝 Visual Studio 2017   
2-1  下載網址如下，選擇免費版的即可   
       https://visualstudio.microsoft.com/downloads/   
2-2  安裝好Visual Studio 2017之後，應該會自動跳出Visual Studio Install 頁面   
2-3  勾選「使用C++的桌面開發」(就是英文教程中的 Desktop development with C++) ，然後點安裝   
   
   
3. 下載並安裝 CUDA Toolkit   
3-1  到tensorflow官網查看支援的CUDA版本，2018年12月時網頁寫支援CUDA 9.0   
       https://www.tensorflow.org/install/gpu   
3-2  到NVIDIA官網，選擇自己的作業系統版本，然後下載CUDA Toolkit 9.0   
       https://developer.nvidia.com/cuda-90-download-archive   
3-3  安裝CUDA 9.0，安裝方式為經典的OK、同意、下一步，在此不贅述   
3-4(選擇性)  如果想看更詳細的CUDA相關資料，官網的網址為   
       https://docs.nvidia.com/cuda/cuda-insta … t-windows/   

4. 下載cuDNN   
4-1  官網的下載頁面會要求註冊   
       https://developer.nvidia.com/rdp/cudnn-download   
4-2  查看對應版本。CUDA 9.0對應的是cuDNN v7.4.1，所以需要下載cuDNN v7.4.1   
   
5. 安裝cuDNN   
5-1  將下載好的cuDNN zip檔解壓縮到桌面，裡面有一個cuda資料夾   
5-2  使用檔案總管，打開本機→C磁碟→Program Files→NVIDIA GPU Computing Toolkit→CUDA→v9.0   
5-3  複製cuda\bin\cudnn64_7.dll，貼到CUDA\v9.0\bin 資料夾裡面   
5-4  複製cuda\include\cudnn.h，貼到CUDA\v9.0\include 資料夾裡面   
5-5  複製cuda\lib\x64\cudnn.lib，貼到CUDA\v9.0\lib\x64 資料夾裡面   
   
6. 下載並安裝Python3.6.6   
6-1  tensorflow不支援32位元的Python，所以要下載64位元版本的   
6-2  我測試時發現tensorflow不支援最新的Python3.7.1。如果安裝的Python太新導致tensorflow不支援，嘗試安裝tensorflow時會出現以下錯誤訊息：   
       Could not find a version that satisfies the requirement tensorflow(from versions:) No matching distribution found for tensorflow   
6-3  筆者測試Python3.6.6 可以安裝tensorflow，所以在此以Python3.6.6為例，下載網址為   
       https://www.python.org/downloads/release/python-366/   
6-4  網頁往下拉，找到 Windows x86-64 executable installer   
6-5  下載完成的檔案，點兩下左鍵進行安裝。安裝時，這個選項一定要打勾 口Add Python 3.6 to PATH   
   
7. Windows環境變數確認   
7-1  在本機上按滑鼠右鍵→選內容→選進階系統設定→切換到「進階」分頁→按環境變數   
7-2  上方是使用者變數欄位，下方是系統變數欄位   
7-3  檢查系統變數欄位中，有沒有變數叫CUDA_PATH   
7-4  檢查變數CUDA_PATH 的值，值是不是C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.0   
7-5(非必要) 關於環境變數設定，網路上有多種說法，我將一些資料附在最後。   
   
8. 安裝tensorflow GPU版本   
8-1  按Windows鍵+R，叫出執行視窗，輸入cmd並執行   
8-2  輸入pip install tensorflow-gpu   
8-3  安裝成功的畫面如下，會看到Successfully installed.....(省略)....tensorflow-gpu-1.12.0...(省略)      
   
參考資料：   
1.  https://www.youtube.com/watch?v=KZFn0dvPZUQ   
2.  https://www.youtube.com/watch?v=HExRhnO5Mqs
3.  https://medium.com/@WhoYoung99/2018%E6%9C%80%E6%96%B0win10%E5%AE%89%E8%A3%9Dtensorflow-gpu-keras-8b3f8652509a
4.  https://www.youtube.com/watch?v=uIm3DMprk7M
