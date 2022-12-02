
# computer_vision

**사용 프로그램**
***
python                    3.9.13    
matplotlib                3.6.1    
numpy                     1.23.4    
opencv-python             4.6.0.66    
pyqt5                     5.15.7   
pyside6                   6.4.0   
pyside2                   5.15.2.1   
***

* 사이즈의 크기를 MainWindow.resize(1046, 804)를 통해 사이즈 조정
* pixmap = pixmap.scaled(QSize(300, 300), aspectMode=Qt.KeepAspectRatioByExpanding) 을 통해 비율 그대로의 사진 받기
* label_3 사진 데이터를  QPixmap객체의 형태로 반환받은 후 변수에 넣어, save함수를 이용해 사진 저장, Saved_image 라는 이름으로 저장

### 자세한 기능 설명 ###
---

* 사진반전 (Flip_image) *
  
  cv2.flip 를 사용하여 사진을 반전하여 보여줍니다.
  
* 색상 반전 (pain_image) *
  
  cv2에 있는 COLOR_BGR2RGB 를 사용하여 색을 반전 시켜주었습니다.
  
*  사진 가져오기 show_file_dialog *
  
  자신의 폴더에 있는 사진을 self.image에 넣어서 가져옵니다.

* 두번째 사진 가져오기 second_image *
  
  자신의 폴더에 있는 사진을 가져오며 self.image2에 넣고 label_5의 위치에 사진이 뜹니다.
  Plus_image라는 사진 두장을 합치는 기능을 위해 만들어놓았습니다. 기능을 쓰기 위해서 먼저 이버튼을 눌러야 합니다.
  
* 사진 합치기 Plus_image *
  
  self.image 와 self.image2를 합치는 기능으로 Load_image버튼으로 먼저 이미지를 불러와주시고, 두번째 이미지 불러오기를 통해 총 사진 2개를 불러주신 뒤 눌러주시면
  사이즈를 조절한 뒤 alpha를 이용하여 사진을 조정해준 뒤 합쳐서 나옵니다.
  
* 모자이크 만들기 Mozaic_image *

  사진을 축소 하고 다시 그 사진을 사진을 사이즈를 지정해주지 않고 다시 조정해주는 식으로 하여 만들었습니다.
  
* 볼록 이미지 Polar_image  *

  exp와 scale 을 이용하여 사진의  극좌표를 변경 했습니다.
  
* 오목 이미지 scale_image *
  
  볼록과 비슷하지만 범위를 바꾸고, 극좌표 또한 변경했습니다.
 
* 흐린 이미지 Blur_image  *
   
  cv2에 있는 medianBlur을 이용하여 블러처리 했습니다.
  
 * HSV 이미지 Hsv_image *
 
   사진을 RGB형태가 아닌 HSV 형태로 받아오기 위해 cv2를 사용했습니다.
---

```python
.
.
        
    def showMessageBox(self):
        msgBox = QMessageBox()
        msgBox.setWindowTitle("Title")
        msgBox.setText("Please insert image on label_3")
        msgBox.setInformativeText("이미지를 넣어주세요.")
        msgBox.setIcon(QMessageBox.Information)
        msgBox.setStandardButtons(QMessageBox.Ok | QMessageBox.Discard | QMessageBox.Cancel)
        msgBox.setDefaultButton(QMessageBox.Ok)
 
        result = msgBox.exec()
        if result == QMessageBox.Ok:
            print("OK")
        elif result == QMessageBox.Cancel:
            print("Cancel")
 .
 .

```
* 위 코드를 사용하여 사진이 없이 plus_image를 시도할시, 메시지를 뜨게 하려 하였으나, 오류로 인해 해결을 완료하지 못했습니다. 
