
# 嵌入式系統 - 實作8: 零基礎Python快速入門與實作

## 暖身: 請同學先參考Lab8-3的程式, 並將鋼琴的圖像在Colab中Show出來. 
![image](https://user-images.githubusercontent.com/89717270/141667140-c50ad364-7478-497b-8339-b368f5fdcceb.png)

## Lab 8-1 零基礎Python快速入門與實作
### 實作P1115 + Final Result
![image](https://user-images.githubusercontent.com/89717270/141667221-2edbce33-a349-4c56-889e-10a80b11e01b.png)

## Lab 8-2 零基礎Python快速入門與實作
### 實作P1185 + Final Result
![image](https://user-images.githubusercontent.com/89717270/142749183-3dfc6368-193a-4ecc-aa97-43e9a4741dd9.png)

## Lab 8-3 建立新的Colab Notebook (e.g., Filename: ShowPhoto.ipynb), 用Python來Show一下圖像, 完成後並更新到GitHub
![image](https://user-images.githubusercontent.com/89717270/142749410-153794a1-5817-472f-8a84-f30bc4fc29ec.png)

### CODE
````C
print('*** Done by %s at ' % ts3,today, type(today))
## Demo: Show tiger

image_name = 'flamingo' 

images_for_test_map = {
    "tiger": "https://upload.wikimedia.org/wikipedia/commons/b/b0/Bengal_tiger_%28Panthera_tigris_tigris%29_female_3_crop.jpg",
    "bus": "https://upload.wikimedia.org/wikipedia/commons/6/63/LT_471_%28LTZ_1471%29_Arriva_London_New_Routemaster_%2819522859218%29.jpg",
    "car": "https://upload.wikimedia.org/wikipedia/commons/4/49/2013-2016_Toyota_Corolla_%28ZRE172R%29_SX_sedan_%282018-09-17%29_01.jpg",
    "cat": "https://upload.wikimedia.org/wikipedia/commons/4/4d/Cat_November_2010-1a.jpg",
    "dog": "https://upload.wikimedia.org/wikipedia/commons/archive/a/a9/20090914031557%21Saluki_dog_breed.jpg",
    "apple": "https://upload.wikimedia.org/wikipedia/commons/1/15/Red_Apple.jpg",
    "turtle": "https://upload.wikimedia.org/wikipedia/commons/8/80/Turtle_golfina_escobilla_oaxaca_mexico_claudio_giovenzana_2010.jpg",
    "flamingo": "https://upload.wikimedia.org/wikipedia/commons/b/b8/James_Flamingos_MC.jpg",
    "piano": "https://upload.wikimedia.org/wikipedia/commons/d/da/Steinway_%26_Sons_upright_piano%2C_model_K-132%2C_manufactured_at_Steinway%27s_factory_in_Hamburg%2C_Germany.png",
    "honeycomb": "https://upload.wikimedia.org/wikipedia/commons/f/f7/Honey_comb.jpg",
    "teapot": "https://upload.wikimedia.org/wikipedia/commons/4/44/Black_tea_pot_cropped.jpg",
}

img_url = images_for_test_map[image_name]
image, original_image = load_image(img_url, image_size, dynamic_size, max_dynamic_size)
show_image(image, 'Scaled image')

print('*** Done by %s at ' % ts3,today, type(today))
````
