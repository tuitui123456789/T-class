
# 實作7: AI-based ES? AI? ML? DL? 要如何入門 (How To Learn)?

## Lab 7-1 在你的Google Drive建立你的第一個Colab Notebook
````
1.安裝Colab
2.新增ES2021的Folder
3.在此Folder下, 建立你的第一個Colab Notebook (i.e. 'hello-ai'). 將你的Google Drive和Google VM (Virtual Machine)掛接
4.在你Colab Notebook顯示以下訊息(OOO: 你的英文名字; e.g., Joe biden)
5.新增文字儲存格 (請用你的英文名字)
````
### 實作成果:
![image](https://user-images.githubusercontent.com/89717270/141666037-bd9841a6-6f08-47b9-9610-69ac5523afbd.png)

## Lab 7-2 暖身: 一起來十分鐘學會Python
````c
# task 1: string variable
name = "TUI"
print(name)

# task 2: number variable
number = 26
print(number)
print(number*3)
print(number/2)
print(number + number)
print(number - number)

# task 3: function

def printName(firstName, lastName):
  print(lastName + ' ' + firstName)

printName('TUI', 'TUI')

# task 4: if else

def printName(firstName, lastName, isCool):
  if isCool:
    print(lastName + ' ' + firstName + ' very cool!')
  else:
    print(lastName + ' ' + firstName + ' not cool!')

# Start
printName('TUI', 'TUI', True)
printName('TUI', 'TIU', False)

# task 5: for loop

def printName(firstName, lastName, isCool, num):
  for i in range(1, num):
    if isCool:
      print(i, lastName + ' ' + firstName + ' very cool!')
    else:
      print(i, lastName + ' ' + firstName + ' not cool!')

# Start
printName('TUI', 'TUI', True, 10)
````

### Task5實作
![image](https://user-images.githubusercontent.com/89717270/141666806-724b7a22-70db-46ea-9eb1-56d65a070de6.png)

## Lab 7-3 確認Lab7完成的兩個Notebook都成功的存在你的雲端硬碟/ES2021目錄下

![image](https://user-images.githubusercontent.com/89717270/141666966-a2d44ad3-e4bc-4670-b562-2a75dd01c19a.png)
