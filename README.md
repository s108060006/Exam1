# Exam1
INPUT設計：
  三個按鈕分別接到D8,D9,D10，三個功能分別為up,down,confirm，設計方式均依照提議要求。按鈕控制方式是用一個Thread每0.3秒去偵測按鈕狀態，如果偵測到按鈕按下，就會執行那個功能，所以按鈕要按稍微長過0.3秒才會有反應。
DISPLAY設計：
  透過ULCD顯示目前選定的Slewrate，初始值為1，如果按下confirm按鈕後，所選定的數值將不再被更改，並且數值會被反白，以示確定。
Generate waveform設計：
  將每一個波分成120個點，每個點的間隔以2ms為間隔，因此可以點出週期為240ms的波型，然後依照所選定的slewrate去畫出所選定的波型，將一個周期的波分成三個段，分別為上升、維持、下降，三個段的長度會照所選定的slewrate做改變。
Measure設計：
  將前者產生的波由PA_4連接至麵包板再連接至picoscope，就可以看到前者所產生的波型，由上傳截圖可知結果。
Sample設計：
  以之前Generate waveform時的畫點間格當作Sampling rate，就可以Sample出完整的波，將取樣到的值先放到一個陣列儲存，取樣結束後再將所取樣到的數值Print到screen上，Python Analysis就可以取得這些值。
Analysis設計：
  透過readline讀取在screen中的值，就可作圖。
