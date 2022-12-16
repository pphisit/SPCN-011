# SPCN-011
 ## 1. สร้าง master vm
### 1.1 คลิ๊กที่ Create VM 
![create](https://user-images.githubusercontent.com/109591322/206201325-5f1f2d2e-8312-4c92-8257-65fee95234cd.png)
### 1.2  ใส่ชื่อเครื่อง 
![create](https://user-images.githubusercontent.com/109591322/206201697-6bf6fd0e-b7f0-4bfc-81ac-8d660a21cc83.png)
ใช้ค่า default ยกเว้น หัวข้อ disks 
Storage ให้เลือกเป็น cept-std

หลังจากนั้นทำการ อัพเกรดและปรับเวลาให้เป็นเวลาไทย

โดยใช้คำสั่งด้านล่างเพื่อปรับเวลา
```
sudo timedatectl set-timezone Asia/Bangkok
```
และ set qemu-guest-agent 


เมื่อทำเสร็จครบหมดแล้วจึงค่อยทำการ clone
## 2.clone master vm to tamplate
เมื่อแปลงให้เป็น template แล้วทำการ clone

![create](https://user-images.githubusercontent.com/109591322/206201786-c29a5c9e-4b0b-4d63-afef-3fcf0d18a054.png)
คลิ๊กขวาเครื่องที่จะทำการ clone แล้วเลือก clone

ทำการ clone 2 ครั้ง (2 vm)
![create](https://user-images.githubusercontent.com/109591322/206201790-63c73a11-05f3-42c3-99c9-efa0fa7f3906.png)

หลังจาก clone 2 เครื่องสำเร็จ ให้เปลี่ยนชื่อ hostname ของทั้ง2เครื่อง 

โดยใช้คำสั่ง

``` 
sudo hostnamectl set-hostname (ชื่อที่จะตั้ง)
```

>Ex. 
sudo hostnamectl set-hostname Pea-clone-1-150

โดยทั้ง2เครื่องผมใช้ชื่อว่า

1.Pea-clone-1-150
![create](https://user-images.githubusercontent.com/109591322/206209560-084541e3-6a17-4aa1-966c-105a9bbd3b90.png)
2.Pea-clone-2-167
![create](https://user-images.githubusercontent.com/109591322/206209587-fd28dc81-ff9c-47f3-9c60-f03e6160ae8c.png)

และทำการตั้งเวลาให้เป็นเวลาไทย โดยใช้คำสั่ง

```
sudo timedatectl set-timezone Asia/Bangkok
```
![create](https://user-images.githubusercontent.com/109591322/206214159-77a4dcb7-984e-4c9a-9a7f-992c14a0cbb2.png)

![create](https://user-images.githubusercontent.com/109591322/206214150-88b01a75-2edd-413a-aed4-1fb0f48970b0.png)


### เปลี่ยนไอดี vm เพื่อขอ ip ใหม่ ไม่ให้ชนกันเนื่องจากการ clone
โดยใช้คำสั่ง

```
- sudo -i //เปลี่ยนมาเป็น root
- nano /etc/machine-id //ลบข้อมูลในไฟล์ทั้งหมด
- ln -s /etc/machine-id /var/lib/dbus/machine-id //เชื่อมข้อมูลเข้ากับ machine-id
- reboot 

ทำแบบนี้กับเครื่อง clone อักอัน
```


## summary ทั้ง 3 เครื่อง
![create](https://user-images.githubusercontent.com/109591322/206209591-b5aac601-be9e-4c0c-ae8c-d516a3afa5a3.png)

![create](https://user-images.githubusercontent.com/109591322/206209566-60668052-b07a-4794-93c1-9d631b522c0e.png)

![create](https://user-images.githubusercontent.com/109591322/206209578-f6675a65-4ff1-41c6-85ac-c7660b8a6c4a.png)

## other os 

![create](https://user-images.githubusercontent.com/109591322/206214109-6419d85f-39d7-4ee6-85e6-8814e6c1500e.png)

## summary and console CT
![create](https://user-images.githubusercontent.com/109591322/206220356-696b5e3e-3585-4e19-b3f1-8ef64d6d1903.png)
![create](https://user-images.githubusercontent.com/109591322/206219800-303fc783-a49e-4a3b-a3be-a65c9bf51b8f.png)